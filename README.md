const invalidCharRegex = /^[\x1F]/;

// Get a list of all collections in the database
const collectionNames = db.getCollectionNames();

// Function to check if a value looks like XML content
const isXmlContent = (value) => typeof value === "string" && value.startsWith("<") && value.endsWith(">");

// Function to recursively search for XML content in an object
const searchXmlContentInObject = (obj, path = []) => {
  for (const key in obj) {
    if (isXmlContent(obj[key])) {
      if (invalidCharRegex.test(obj[key])) {
        return { fieldName: [...path, key].join('.'), content: obj[key] };
      }
    } else if (typeof obj[key] === "object") {
      const result = searchXmlContentInObject(obj[key], [...path, key]);
      if (result) {
        return result;
      }
    }
  }
  return null;
};

// Iterate over each collection and find documents with the invalid character
collectionNames.forEach((collectionName) => {
  print(`Checking collection: ${collectionName}`);

  const cursor = db[collectionName].find({});

  while (cursor.hasNext()) {
    const doc = cursor.next();
    const result = searchXmlContentInObject(doc);

    if (result) {
      print(`Found invalid document in '${collectionName}':`);
      printjson({ _id: doc._id, fieldName: result.fieldName, content: result.content });
    }
  }

  print("\n");
});

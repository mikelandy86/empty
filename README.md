const dbName = "myDatabase";
const database = db.getSiblingDB(dbName);
const collections = database.getCollectionNames();

collections.forEach(collectionName => {
    const collectionInfo = database.runCommand({ listCollections: 1, filter: { name: collectionName } });
    const validator = collectionInfo.cursor.firstBatch[0].options && collectionInfo.cursor.firstBatch[0].options.validator;
    
    if (validator) {
        print(`Collection '${collectionName}' has the following validation rule: ${JSON.stringify(validator)}`);
    }
});

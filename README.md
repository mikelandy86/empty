db.getCollectionNames().forEach(function(collection) {
  var collStats = db.runCommand({collStats: collection});
  if (collStats.validator || collStats.partialFilterExpression) {
    print("Collection:", collection);
    printjson(collStats);
  }
});

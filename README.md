db.getCollectionNames().forEach(function(collection) {
  var coll = db.getCollection(collection);
  var options = coll.options();
  if (options.validator || options.partialFilterExpression) {
    print("Collection:", collection);
    printjson(options);
  }
});

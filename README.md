db.getCollectionNames().forEach(function(collection) {
  var indexes = db[collection].getIndexes();
  print("Indexes for collection '" + collection + "':");
  printjson(indexes);
});

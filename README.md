db.getCollectionNames().forEach(function(collection) {
    var coll = db.getCollection(collection);
    if (coll.isView()) {
        print("View name: " + coll.getName());
    }
});

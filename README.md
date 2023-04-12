function listValidationRules() {
    const collections = db.getCollectionNames();
    collections.forEach(collectionName => {
        const collectionInfo = db.runCommand({ listCollections: 1, filter: { name: collectionName } });
        const validator = collectionInfo.cursor.firstBatch[0].options && collectionInfo.cursor.firstBatch[0].options.validator;
        if (validator) {
            print(`Collection '${collectionName}' has the following validation rule: ${JSON.stringify(validator)}`);
        }
    });
}

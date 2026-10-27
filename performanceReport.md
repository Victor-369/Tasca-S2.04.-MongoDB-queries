1. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


2. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0,restaurant_id:1,name:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


3. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


4. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0,restaurant_id:1,name:1,borough:1,"address.zipcode":1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## ✅ No significant issues detected


5. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:"Bronx"},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 54
- 🔍 **Documents examined**: 54
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


6. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:"Bronx"},{_id:0}).limit(5)`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 5
- 🔍 **Documents examined**: 5
- 🛠️ **Execution stage**: LIMIT

## ✅ No significant issues detected


7. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:"Bronx"},{_id:0}).skip(5).limit(5)`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 5
- 🔍 **Documents examined**: 5
- 🛠️ **Execution stage**: LIMIT

## ✅ No significant issues detected


8. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.score":{$gt:90}},{_id:0})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 2 (ratio 332.0:1)

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ grades.score: 1 });
```


9. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({grades:{$elemMatch:{score:{$gt:80,$lt:100}}}},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)


10. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"location.coordinates.0":{$lt:-95.754168}},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 0
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


11. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({$and:[{"location.coordinates.0":{$lt:-65.754168}},{cuisine:{$ne:"American"}},{grades:{$elemMatch:{score:{$gt:70}}}}]},{_id:0})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 403
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 403 docs to return 1 (ratio 403.0:1)


12. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"location.coordinates.0":{$lt:-65.754168},cuisine:{$ne:'American'},grades:{$elemMatch:{score:{$gt:70}}}},{_id:0})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 403
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 403 docs to return 1 (ratio 403.0:1)


13. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({cuisine:{$ne:"American"},borough:{$ne:"Brooklyn"},"grades.grade":"A"},{_id:0}).sort({cuisine:-1})`
- ⏱️ **Execution time**: 3 ms
- 📚 **Documents returned**: 318
- 🔍 **Documents examined**: 403
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


14. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({name:{$regex:"^Wil"}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 2
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


15. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({name:{$regex:"ces$"}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 2
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


16. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({name:{$regex:"Reg"}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 4
- 🔍 **Documents examined**: 4
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


17. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:"Bronx",cuisine:{$in:["American","Chinese"]}},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 22
- 🔍 **Documents examined**: 54
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


18. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:{$in:["Staten Island","Queens","Bronx","Brooklyn"]}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 359
- 🔍 **Documents examined**: 359
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


19. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough:{$nin:["Staten Island","Queens","Bronx","Brooklyn"]}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 305
- 🔍 **Documents examined**: 305
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


20. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.score":{$lte:10}},{_id:0,restaurant_id:1,name:1,borough:1,cuisine:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 612
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ grades.score: 1 });
```


21. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({$or:[{name:{$regex:"^Wil"}},{$and:[{cuisine:"Seafood"},{cuisine:{$nin:["American","Chinese"]}}]}]},{_id:0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 14
- 🔍 **Documents examined**: 14
- 🛠️ **Execution stage**: SUBPLAN

## ✅ No significant issues detected


22. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({grades:{$elemMatch:{grade:"A",score:11,date:ISODate("2014-08-11T00:00:00Z")}}},{_id:0,restaurant_id:1,name:1,grades:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)


23. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.1":{grade:"A",score:9,date:ISODate("2014-08-11T00:00:00Z")}},{_id:0,restaurant_id:1,name:1,grades:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 0
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


24. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({location:{$near:{$geometry:{type:"Point",coordinates:[-74,40.7]},$maxDistance:5000}}},{_id:0,restaurant_id:1,name:1,"address.street":1,"address.zipcode":1,"location.coordinates":1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 147
- 🔍 **Documents examined**: 206
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## ✅ No significant issues detected


25. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0}).sort({name:1})`
- ⏱️ **Execution time**: 2 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


26. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0}).sort({name:-1})`
- ⏱️ **Execution time**: 2 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


27. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({},{_id:0}).sort({cuisine:1,borough:-1})`
- ⏱️ **Execution time**: 2 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: SORT

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ‼️ Sorting on unindexed field 'cuisine' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ cuisine: 1 });
```


28. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({$or:[{},{"address.street":""}]},{_id:0,address:1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'address.street' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ address.street: 1 });
```


29. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"location.coordinates":{$type:"double"}},{_id:0,name:1,restaurant_id:1,"location.coordinates":1})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## 🚨 Performance Issues

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'location.coordinates' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ location.coordinates: 1 });
```


30. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.score":{$mod:[7,0]}},{_id:0,restaurant_id:1,name:1,"grades.grade":1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 262
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## 🚨 Performance Issues

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ grades.score: 1 });
```


31. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({name:{$regex:"mon"}},{_id:0,name:1,borough:1,"location.coordinates":1,cuisine:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 7
- 🔍 **Documents examined**: 7
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## ✅ No significant issues detected


32. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({grades:{$elemMatch:{score:{$gt:80,$lt:100}}}},{_id:0,restaurant_id:1,name:1,grades:1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)



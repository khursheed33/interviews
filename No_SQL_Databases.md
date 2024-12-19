# MongoDB Complete Guide

## Table of Contents
1. [Introduction to MongoDB](#introduction)
2. [Core Concepts](#core-concepts)
3. [CRUD Operations](#crud-operations)
4. [Aggregation Framework](#aggregation-framework)
5. [Indexing](#indexing)
6. [Replication and Sharding](#replication-and-sharding)
7. [Security](#security)
8. [Python Integration](#python-integration)
9. [Best Practices](#best-practices)
10. [Interview Questions](#interview-questions)

## Introduction

MongoDB is a popular NoSQL database that stores data in flexible, JSON-like documents. Unlike traditional relational databases, MongoDB doesn't require a predefined schema, making it ideal for applications with evolving data requirements.

### Key Features
- Document-oriented storage
- High scalability
- Rich query language
- High availability
- Support for multiple storage engines

## Core Concepts

### Document Model
MongoDB stores data in documents, which are organized into collections. A document is a set of key-value pairs similar to JSON objects.

Example document:
```json
{
    "_id": ObjectId("5f7d3b3b1c9d440000f1c2d3"),
    "name": "John Doe",
    "age": 30,
    "email": "john@example.com",
    "address": {
        "street": "123 Main St",
        "city": "New York",
        "country": "USA"
    },
    "hobbies": ["reading", "swimming"]
}
```

### Collections
Collections are groups of documents. They are analogous to tables in relational databases but don't enforce a schema.

### Database
A MongoDB instance can host multiple databases, each containing its own collections.

## CRUD Operations

### Creating Documents
Python example using PyMongo:
```python
from pymongo import MongoClient

# Connect to MongoDB
client = MongoClient('mongodb://localhost:27017/')
db = client['example_db']
collection = db['users']

# Insert one document
user = {
    "name": "John Doe",
    "age": 30,
    "email": "john@example.com"
}
result = collection.insert_one(user)
print(f"Inserted document ID: {result.inserted_id}")

# Insert multiple documents
users = [
    {"name": "Alice", "age": 25},
    {"name": "Bob", "age": 35}
]
result = collection.insert_many(users)
print(f"Inserted document IDs: {result.inserted_ids}")
```

### Reading Documents
```python
# Find one document
user = collection.find_one({"name": "John Doe"})

# Find multiple documents
users = collection.find({"age": {"$gt": 25}})
for user in users:
    print(user)

# Query with multiple conditions
users = collection.find({
    "$and": [
        {"age": {"$gte": 25}},
        {"age": {"$lte": 35}}
    ]
})
```

### Updating Documents
```python
# Update one document
result = collection.update_one(
    {"name": "John Doe"},
    {"$set": {"age": 31}}
)

# Update multiple documents
result = collection.update_many(
    {"age": {"$lt": 30}},
    {"$inc": {"age": 1}}
)
```

### Deleting Documents
```python
# Delete one document
result = collection.delete_one({"name": "John Doe"})

# Delete multiple documents
result = collection.delete_many({"age": {"$lt": 25}})
```

## Aggregation Framework

The aggregation framework is MongoDB's pipeline-based data processing tool.

Example aggregation:
```python
pipeline = [
    # Match stage
    {"$match": {"age": {"$gte": 25}}},
    
    # Group stage
    {"$group": {
        "_id": "$city",
        "avg_age": {"$avg": "$age"},
        "total_users": {"$sum": 1}
    }},
    
    # Sort stage
    {"$sort": {"avg_age": -1}}
]

results = collection.aggregate(pipeline)
```

Common Aggregation Operators:
- `$match`: Filters documents
- `$group`: Groups documents by a specified expression
- `$sort`: Sorts documents
- `$project`: Reshapes documents
- `$lookup`: Performs a left outer join
- `$unwind`: Deconstructs an array field

## Indexing

Indexes improve query performance by reducing the number of documents MongoDB needs to scan.

```python
# Create a single field index
collection.create_index("email", unique=True)

# Create a compound index
collection.create_index([("age", 1), ("city", -1)])

# Create a text index
collection.create_index([("description", "text")])
```

Types of Indexes:
1. Single Field Index
2. Compound Index
3. Multikey Index (for arrays)
4. Text Index
5. Geospatial Index
6. Hashed Index

## Replication and Sharding

### Replication
Replication provides redundancy and high availability:
- Primary node receives all writes
- Secondary nodes maintain copies of data
- Automatic failover if primary becomes unavailable

```python
# Connect to a replica set
client = MongoClient('mongodb://localhost:27017/?replicaSet=rs0')
```

### Sharding
Sharding distributes data across multiple machines:
- Horizontal scaling
- Automatic balancing
- Transparent to applications

## Security

### Authentication
```python
# Connect with authentication
client = MongoClient('mongodb://username:password@localhost:27017/')
```

Security Best Practices:
1. Enable authentication
2. Use role-based access control (RBAC)
3. Encrypt data in transit
4. Enable audit logging
5. Regular security audits

## Best Practices

1. Schema Design
   - Embed related data when possible
   - Use references for large or frequently changing data
   - Consider read/write patterns

2. Performance
   - Use appropriate indexes
   - Avoid large documents
   - Use projection to limit returned fields
   - Batch operations when possible

3. Data Modeling
   - Plan for scaling
   - Consider document growth
   - Use appropriate data types

## Interview Questions

### Basic Level

#### Conceptual Questions
1. **Q: What is MongoDB and how is it different from SQL databases?**
   A: MongoDB is a NoSQL database that stores data in flexible, JSON-like documents. Unlike SQL databases, it doesn't require a predefined schema and can handle complex, nested data structures naturally.

2. **Q: Explain the concept of _id in MongoDB.**
   A: _id is a unique identifier automatically generated for each document if not specified. It's a 12-byte ObjectId by default, containing timestamp, machine ID, process ID, and counter.

### Intermediate Level
3. **Q: How does indexing work in MongoDB?**
   A: Indexes in MongoDB are special data structures that store a small portion of the collection's data in an easy-to-traverse form. They improve query performance by reducing the number of documents MongoDB needs to scan.

4. **Q: Explain the aggregation pipeline.**
   A: The aggregation pipeline is a framework for data processing that consists of stages. Each stage transforms documents as they pass through the pipeline. Common stages include $match, $group, $sort, and $project.

### Intermediate Level (continued)

5. **Q: What are the different types of NoSQL databases? How does MongoDB compare to them?**
   A: There are four main types of NoSQL databases:
   - Document stores (MongoDB, CouchDB)
   - Key-value stores (Redis, DynamoDB)
   - Column-family stores (Cassandra, HBase)
   - Graph databases (Neo4j, ArangoDB)
   MongoDB is a document store that offers:
   - Rich query language compared to key-value stores
   - Better handling of complex relationships than column-family stores
   - More flexible scaling than graph databases
   - Better performance for most general-purpose applications

6. **Q: Explain the difference between references and embedded documents.**
   A: 
   - Embedded documents: Stored within the parent document
     ```json
     {
       "order_id": 1,
       "customer": {
         "name": "John",
         "address": "123 Street"
       }
     }
     ```
   - References: Store a reference to another document
     ```json
     {
       "order_id": 1,
       "customer_id": ObjectId("123")
     }
     ```
   Choose embedding for:
   - One-to-one relationships
   - Small, rarely-changing embedded data
   - Data that's always queried together
   
   Choose references for:
   - One-to-many or many-to-many relationships
   - Large documents
   - Data that changes frequently
   - Data that needs to be accessed independently

7. **Q: What are the different read concerns in MongoDB and when would you use each?**
   A: MongoDB offers several read concerns:
   - `local`: Returns data from the instance, no guarantee of durability
   - `available`: Returns data from the instance, no guarantee of consistency
   - `majority`: Returns data acknowledged by majority of replicas
   - `linearizable`: Guarantees reading most recent write operation
   Use cases:
   - `local`: Fast reads where consistency isn't critical
   - `majority`: When strong consistency is required
   - `linearizable`: When absolute consistency is required for single-document reads

8. **Q: How do you handle schema changes in MongoDB?**
   A: MongoDB supports several strategies for schema evolution:
   1. Add fields: New fields can be added without affecting existing documents
   2. Rename fields: Use `$rename` operator in an update operation
   3. Remove fields: Use `$unset` operator
   4. Transform data: Use aggregation pipeline or update operations
   Example:
   ```python
   # Adding a new field with a default value
   db.users.update_many(
       {"new_field": {"$exists": False}},
       {"$set": {"new_field": "default_value"}}
   )
   ```

### Advanced Level

9. **Q: How does MongoDB handle concurrency?**
   A: MongoDB uses a combination of write locks at the database level and document-level locking for WiredTiger storage engine. It implements optimistic concurrency control using versions.

6. **Q: Explain sharding architecture and when to use it.**
   A: Sharding is MongoDB's approach to horizontal scaling. It distributes data across multiple machines using:
   - mongos (router)
   - config servers (metadata)
   - shard servers (data)
   Use sharding when:
   - Dataset exceeds single server capacity
   - Write throughput exceeds capability
   - Working set doesn't fit in RAM

7. **Q: How would you optimize a slow MongoDB query?**
   A: Steps to optimize:
   1. Use explain() to analyze query performance
   2. Create appropriate indexes
   3. Use proper projection
   4. Consider query patterns
   5. Review index usage
   6. Check for proper shard key if using sharding

15. **Q: What is the difference between `$lookup` and `$graphLookup`? When would you use each?**
    A: 
    - `$lookup`: Performs a left outer join with another collection
      ```javascript
      {
        $lookup: {
          from: "inventory",
          localField: "item",
          foreignField: "_id",
          as: "inventory_docs"
        }
      }
      ```
    - `$graphLookup`: Performs a recursive search on a collection
      ```javascript
      {
        $graphLookup: {
          from: "employees",
          startWith: "$reportsTo",
          connectFromField: "reportsTo",
          connectToField: "_id",
          as: "reportingHierarchy"
        }
      }
      ```
    Use `$lookup` for simple joins, `$graphLookup` for hierarchical/graph data.

16. **Q: How would you model a time series data in MongoDB?**
    A: Several approaches:
    1. Bucketing pattern:
    ```javascript
    {
      timestamp_hour: ISODate("2024-01-01T00:00:00Z"),
      measurements: [
        { timestamp: ISODate("2024-01-01T00:01:00Z"), value: 22 },
        { timestamp: ISODate("2024-01-01T00:02:00Z"), value: 23 }
      ]
    }
    ```
    2. Time-based collections:
    ```javascript
    db.measurements_2024_01
    db.measurements_2024_02
    ```
    3. Using MongoDB Time Series Collections (5.0+):
    ```javascript
    db.createCollection("weather", {
      timeseries: {
        timeField: "timestamp",
        metaField: "metadata",
        granularity: "hours"
      }
    })
    ```

17. **Q: Explain how you would implement optimistic locking in MongoDB.**
    A: Optimistic locking can be implemented using a version field:
    ```python
    def update_with_version(collection, doc_id, updates, version):
        result = collection.update_one(
            {
                "_id": doc_id,
                "version": version
            },
            {
                "$set": updates,
                "$inc": {"version": 1}
            }
        )
        if result.modified_count == 0:
            raise ConcurrentModificationError()
        return result
    ```

18. **Q: How would you handle data migration and schema updates in a production environment?**
    A: Best practices include:
    1. Incremental updates:
    ```python
    def migrate_schema_v1_to_v2():
        batch_size = 1000
        last_id = None
        while True:
            query = {} if last_id is None else {"_id": {"$gt": last_id}}
            batch = db.collection.find(query).limit(batch_size)
            if not batch:
                break
            for doc in batch:
                # Update schema
                db.collection.update_one(
                    {"_id": doc["_id"]},
                    {"$set": {"new_field": transform(doc["old_field"])}}
                )
                last_id = doc["_id"]
    ```
    2. Dual-write pattern for zero-downtime migrations
    3. Feature flags for gradual rollout
    4. Backup and rollback plans

19. **Q: Explain MongoDB's storage engine options and their trade-offs.**
    A: MongoDB supports multiple storage engines:
    1. WiredTiger (default):
        - Document-level concurrency
        - Compression
        - Better performance for most workloads
    2. In-Memory:
        - Faster operations
        - No persistence
        - Limited by RAM
    3. Encrypted:
        - Built-in encryption
        - Additional CPU overhead
    Choose based on:
    - Performance requirements
    - Durability needs
    - Security requirements
    - Memory constraints

20. **Q: Describe MongoDB's consistency model.**
   A: MongoDB provides:
   - Strong consistency for standalone instances
   - Eventual consistency in replicated environments
   - "read your own writes" consistency
   - Configurable read concerns (local, majority, linearizable)

## Python Integration Examples

### Connection Pooling
```python
from pymongo import MongoClient
from pymongo.errors import ConnectionFailure

def get_database():
    try:
        client = MongoClient(
            'mongodb://localhost:27017/',
            maxPoolSize=50,
            waitQueueTimeoutMS=2500
        )
        return client['example_db']
    except ConnectionFailure:
        print("Failed to connect to MongoDB")
        return None
```

### Bulk Operations
```python
from pymongo import UpdateOne, DeleteOne

def bulk_update_users(collection, updates):
    operations = []
    for update in updates:
        operations.append(
            UpdateOne(
                {"_id": update["id"]},
                {"$set": update["data"]}
            )
        )
    
    if operations:
        result = collection.bulk_write(operations, ordered=False)
        return result.modified_count
    return 0
```

### Transaction Example
```python
def transfer_funds(db, from_account, to_account, amount):
    with db.client.start_session() as session:
        with session.start_transaction():
            db.accounts.update_one(
                {"_id": from_account},
                {"$inc": {"balance": -amount}},
                session=session
            )
            
            db.accounts.update_one(
                {"_id": to_account},
                {"$inc": {"balance": amount}},
                session=session
            )
```

### Error Handling
```python
from pymongo.errors import DuplicateKeyError, OperationFailure

def safe_insert(collection, document):
    try:
        result = collection.insert_one(document)
        return result.inserted_id
    except DuplicateKeyError:
        print("Document with this key already exists")
    except OperationFailure as e:
        print(f"Operation failed: {e}")
    return None
```

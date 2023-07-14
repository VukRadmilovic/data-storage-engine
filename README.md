# Key-Value data storage engine

## Tech Stack
- Golang

## Description
This project is a Key-Value engine designed for storing data efficiently. It focuses on optimizing the write and read paths, implementing caching, and utilizing various data structures to improve performance. The project was developed as a console application in Golang.

## Key features
- Write-Ahead Log (WAL): PUT requests are logged in the WAL before being processed.
- Memtable: Data from the WAL is stored in memory in a Memtable until a predefined size is reached.
- SSTable: When the Memtable reaches its size limit, the data is sorted by key and written to disk as an SSTable.
- Read Path: GET requests check the Cache structure first, followed by the Bloom Filter, Summary range, Index file, and Data file.
- Data Structures: The project includes appropriate data structures for efficient storage, such as a Data file, Bloom Filter, Index, Summary, Metadata, and Merkle tree.
- Configuration: The project uses external configuration files for settings such as segment size, number of records in the Memtable, number of LSM tree levels, etc.
- Caching: Implemented an LRU cache algorithm to improve read performance.
- LSM Trees: Organized the project using LSM trees, with multiple levels of Memtable and SSTable.
- Compactions: Provided manual compaction functionality to optimize storage and performance.
- Rate Limiting: Implemented rate limiting using the Token Bucket algorithm to control the system's access rate.
- HyperLogLog (HLL) and Count-Min-Sketch (CMS) support.

## How to Run
1. Clone the repository
2. Navigate to the project directory
3. Build and run the application using the Golang compiler:
```
go run main.go
```

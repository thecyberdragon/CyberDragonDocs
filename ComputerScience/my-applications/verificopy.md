# ✅ Verificopy

#### Setup Requirements

* SQLite or local SQL
* Framenet 5.0
* Database connection string

#### Use Cases

* Standalone software
* Network-monitored standalone software
* Node in hive controlled by a user

### Threading

Each copy will have 2x threads Thread 1: Source checksum Thread 2: Copy and destination checksum\
User can set threads by increment of 2, or - Smart threading which monitors RAM and CPU usage

A background worker will create and activate threads based on the current count

### Dev / Debug Options

* Ram monitoring & tweaking
* Speed transfer feedback
* Error log generation
* Configure complete table retention
* Configure incomplete table retention
* Flush all tables

### UI Options

* RAM usage
* Average speed
* Files per minute
* Active threads
* Source files, sizes, hashes
* Destination files, sizes, hashes
* Copy job and location

Treeview populates with directory which links to specific folder or file information feedback.

* Progress bars (scales with threading)
* Source hash
* Copy
* Destination hash
* Total progress (copies)
* Total progress (hashes)

### Features

* Copy all or use treeview to specify folders
* Second backup location (optional skip checksum)
* Third backup location (optional skip checksum)
* Inclusion list
* Exclusion list
* Continuous sync
* Broadcast tables to network SQL
* Enable as node
* Exception retry count
* Copy into folder
* Log folder


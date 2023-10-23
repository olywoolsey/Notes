#COMP1121
## What is a Transaction
- Action, or series of actions, carried out by user or application, which reads or updates contents of database
	- Logical unit of work on the database
	- Application program is series of transactions with non-database processing in between
	- Transforms database from one consistent state to another, although consistency may be violated during transaction
- Can have one of two outcomes:
	- Success - transaction commits and database reaches a new consistent state
	- Failure - transaction aborts, and database must be restored to consistent state before it started
	- Such a transaction is rolled back or undone
- Committed transaction cannot be aborted
- Aborted transaction that is rolled back can be restarted later

## Properties Of Transactions
- **ACID**
	- **A**tomicity -‘All or nothing’ property
	- **C**onsistency - Must transform database from one consistent state to another
	- **I**solation - Partial effects of incomplete transactions should not be visible to other transactions
	- **D**urability - Effects of a committed transaction are permanent and must not be lost because of later failure

## Concurrency Control
- Manage simultaneous operations on the database without interfering with each other
- Prevents interference when two or more users are accessing database simultaneously and at least one is updating data
- Although two transactions may be correct in themselves, interleaving of operations may produce an incorrect result
### Problems
#### Lost Update Problem
- Successfully completed update is overridden by another user
#### Uncommitted Dependency Problem
- Occurs when one transaction can see intermediate results of another transaction before it has committed
#### Inconsistent Analysis Problem
- Occurs when transaction reads several values but second transaction updates some of them during execution of first

## Serialisability
- Serialisability as a means of helping to identify those executions of transactions that are guaranteed to ensure consistency, as if the transactions are run in serial execution
- Schedule - A sequence of the operations (read, write)by a set of concurrent transactions (T1, T2, ..., Tn) that preserves the order of the operations in each of the individual transactions
- Serial schedule – a schedule with transactions running in serial order, one after another (eg T1 followed by T2)
- Nonserial schedule – a schedule with interleaved transactions
- Nonserial schedule is correct if it produces the same result as some serial execution.
- In serialisability, ordering of read/writes is important
	- If two transactions only read a data item, they do not conflict and order is not important
	- If two transactions either read or write separate data items, they do not conflict and order is not important
	- If one transaction writes a data item and another reads or writes same data item, order of execution is important

## Locking
- Optimistic as assumes conflict is rare and only checks for conflict at commits
- Transaction uses locks to deny access to other transactions and so prevent incorrect updates
- Two types
	- Shared lock for reading data item
	- Exclusive lock for both reading & writing data item
- Reads cannot conflict, so more than one transaction can hold shared locks simultaneously on same item
- Using a Lock:
	1. Any transaction that needs to access a data item must first lock the item
	2. If the item is not already locked by another transaction, the lock will be granted
	3. If the item is locked, the DBMS determines whether the request is compatible with the existing lock. If a shared lock is requested on an item with a shared lock on it, the request will be granted; otherwise, the transaction must wait until the existing lock is released
	4. A transaction continues to hold a lock until it explicitly releases it. It is only when the exclusive lock has been released that effects of the write operation will be made visible to other transactions
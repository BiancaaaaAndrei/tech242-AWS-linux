# Amazon QLDB (Quantum Ledger Database) Overview

Amazon QLDB is a fully managed, serverless, particularly suitable for recording financial transactions.

## Key Features of Amazon QLDB

- **Ledger Database:** QLDB acts as a ledger, recording financial transactions and providing a historical view of changes made to application data over time.
- **Immutable System:** Once data is written to the database, it cannot be removed or modified, ensuring the integrity of financial transactions.
- **Journal and Hashing:** Behind the scenes, QLDB maintains a journal with a sequence of modifications, and cryptographic hashing guarantees data integrity.
- **Performance:** Offers two to three times better performance compared to common ledger blockchain frameworks.
- **SQL Manipulation:** Data in QLDB can be manipulated using SQL.

## How QLDB Works

- **Journal and Cryptographic Hashing:** A journal records modifications with cryptographic hashing to ensure the integrity of the ledger. Anyone can verify that no data has been deleted or modified.

## Exam Tips

- **Ledger Database:** When ledger functionality or financial transactions are mentioned, think of Amazon QLDB.
- **Comparison with Managed Blockchain:** QLDB has a central authority component, while Managed Blockchain involves decentralization.


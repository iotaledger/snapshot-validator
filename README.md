# IOTA Snapshot Validator

A simple Node.js program to validate an IOTA snapshot.

## Installation and use

**Step 1.** Before installation, install `Snapshot.ixi`: `cd` into your `iri` folder, and then:

```
cd ixi
git clone https://github.com/iotaledger/Snapshot.ixi.git Snapshot
```

**Step 2.** You should have Node.js and `npm` installed. Then clone this repo and install:

```
git clone https://github.com/iotaledger/snapshot-validator.git
cd snapshot-validator
npm install
```

**Step 3.** Configure the local node and snapshot URLs.

Open `validate.js` in an editor, and set the `iotaNode` and `snapshotUrl` variables appropriately. The `snapshotUrl` should point to the `Snapshot.txt` file included with a snapshot Pull Request to iotaledger/iri. Using the January 28, 2018 snapshot as an example:

1. Locate the pull request files: https://github.com/iotaledger/iri/pull/989/files
2. Find SnapshotMainnet.txt and click the "View" button
3. Click "View Raw"
4. Copy the URL *after* the page loads - this should be used as the `snapshotUrl` in `validate.js`.

**Step 4.** You are now ready to run the validator:

```
npm start
```

You will see 3 values output from the program upon successful validation of the `Snapshot.txt` file against the current database running on your node:

```
BALANCE CORRECT: <boolean>
VALIDATING SNAPSHOT ENTRIES: <num. of entries>
LATEST STATE EQUALS SNAPSHOT: <boolean>
```

In case of a balance-mismatch error, you will see the following:

```
FATAL ERROR: Balance incorrect for: <address>
Balance (proposed snapshot vs. local): <snapshot balance, local balance>
```

**Step 5.** Please copy-paste these outputs into the PR for the snapshot you are attempting to validate.

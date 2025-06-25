---
description: Portex Game Record provides cloud save functionality for game users.
icon: floppy-disks
---

# Game Record

## API Documentation

* Get Game Record

```typescript
getGameRecord(name: string): Promise<GameRecordResult>
```

* Set Game Record

```typescript
saveGameRecord(name: string, record: string): Promise<boolean>
```

* List Game Record

```typescript
listGameRecordNames(): Promise<ListGameRecordNamesResult>
```

## Interface

```typescript
interface GameRecordResult {
    record: string;
}

interface ListGameRecordNamesResult {
    names: string[];
}
```

## Notes

* `record` string must be base64 string

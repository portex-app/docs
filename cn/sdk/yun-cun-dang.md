---
description: Portex Game Record 为游戏提供云存档功能
icon: floppy-disks
---

# 云存档

## API 文档

* 获取游戏云存档数据

```typescript
getGameRecord(name: string): Promise<GameRecordResult>
```

* 写入游戏云存档数据

```typescript
saveGameRecord(name: string, record: string): Promise<boolean>
```

* 列出当前用户下所有云存档

```typescript
listGameRecordNames(): Promise<ListGameRecordNamesResult>
```

## 接口

```typescript
interface GameRecordResult {
    record: string;
}

interface ListGameRecordNamesResult {
    names: string[];
}
```

## 注意事项

* `record` 字符串，必须是 base64 的格式

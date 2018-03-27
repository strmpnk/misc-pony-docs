No package doc string provided for wallaroo/ent/recovery.

## Public Types

* [primitive StepStateSnapshotter](wallaroo-ent-recovery-StepStateSnapshotter.md)
* [primitive StepLogEntryReplayer](wallaroo-ent-recovery-StepLogEntryReplayer.md)
* [actor RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer.md)
* [primitive CheckCounts](wallaroo-ent-recovery-CheckCounts.md)
* [actor Recovery](wallaroo-ent-recovery-Recovery.md)
* [interface Resilient](wallaroo-ent-recovery-Resilient.md)
* [class EventLogConfig](wallaroo-ent-recovery-EventLogConfig.md)
* [actor EventLog](wallaroo-ent-recovery-EventLog.md)
* [type LogEntry](wallaroo-ent-recovery-LogEntry.md)
* [type ReplayEntry](wallaroo-ent-recovery-ReplayEntry.md)
* [primitive HexOffset](wallaroo-ent-recovery-HexOffset.md)
* [primitive FilterLogFiles](wallaroo-ent-recovery-FilterLogFiles.md)
* [primitive LastLogFilePath](wallaroo-ent-recovery-LastLogFilePath.md)
* [trait Backend](wallaroo-ent-recovery-Backend.md)
* [class DummyBackend](wallaroo-ent-recovery-DummyBackend.md)
* [class FileBackend](wallaroo-ent-recovery-FileBackend.md)
* [class RotatingFileBackend](wallaroo-ent-recovery-RotatingFileBackend.md)
* [type DeduplicationList](wallaroo-ent-recovery-DeduplicationList.md)
* [primitive MessageDeduplicator](wallaroo-ent-recovery-MessageDeduplicator.md)


## Private Types

* [interface _RecoveryReplayer](wallaroo-ent-recovery-_RecoveryReplayer.md)
* [trait _ReplayPhase](wallaroo-ent-recovery-_ReplayPhase.md)
* [class _EmptyReplayPhase](wallaroo-ent-recovery-_EmptyReplayPhase.md)
* [class _AwaitingRecoveryReplayStart](wallaroo-ent-recovery-_AwaitingRecoveryReplayStart.md)
* [class _ReadyForNormalProcessing](wallaroo-ent-recovery-_ReadyForNormalProcessing.md)
* [class _WaitingForBoundaryCounts](wallaroo-ent-recovery-_WaitingForBoundaryCounts.md)
* [class _WaitForReconnections](wallaroo-ent-recovery-_WaitForReconnections.md)
* [class _Replay](wallaroo-ent-recovery-_Replay.md)
* [trait _RecoveryPhase](wallaroo-ent-recovery-_RecoveryPhase.md)
* [class _NotRecovering](wallaroo-ent-recovery-_NotRecovering.md)
* [class _LogReplay](wallaroo-ent-recovery-_LogReplay.md)
* [class _BoundaryMsgReplay](wallaroo-ent-recovery-_BoundaryMsgReplay.md)

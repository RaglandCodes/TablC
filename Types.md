ConnectionType: CSV | Parquet | DuckDB | SQLServer | Oracle | MongoDB | Snowflake | BigQuery
ConnectionLocation: LocalPath | S3Path | __EachDBProvider__ConnectionString

Connection
FriendlyName: String
Type: ConnectionType
Location: ConnectionLocation
ShadowType?: ConnectionType
ShadowConnectionLocation?: ConnectionLocation
...TODO source speciic settings ...
CreatedTs: DataTime
LastConnectionAttemptTs: DataTime
LastConnectionResult: NeverConnected | ConnectedSuccesfully | ConnectionFailed
MaxConnectionAttemptDurationSecond: int
MaxQueryAttemptDurationSecond: int

Connection Collection: 
Name: String
Connections: List[Connection]


DataDisplayTable
Query: String
Name: String
Connection: Connection
Frames?: [DataDisplayFrame]
AutoRefreshFrequency?: int


DataDisplayColumn
Type: int | String | DateTime ......
StatMin?: Number | DateTime
StatMax?: Number | DataTime
StatNullable?: Bool
DistinctValuesCount?: Int
Count?



DataDisplayCell
DisplayString: String
Column: DataDisplayColumn

DataDisplayRow: List[DataDisplayCell]

DataDisplayFrame:
Rows?: List[DataDisplayRow]
Sentinel?: IsFirst | IsLast
DataFetchStatus: NotStarted | InProgress | Completed_Successfully | Completed_Errored
NextPointer: FileByteOffset | RowOffset | .....TODO cursor, etc for each source ..
FetchedAtTs: DataTime
FetchDurationMs: int




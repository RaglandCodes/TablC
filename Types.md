Connection
FriendlyName: String
Type: CSV | Parquet | DuckDB | SQLServer | Oracle | MongoDB | Snowflake | BigQuery
Location: LocalPath | S3Path | __EachDBProvider__ConnectionString



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
NextPointer: FileByterOffset | RowOffset | .....TODO





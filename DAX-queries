Filter by substring in a field
FILTER(
    TableName,
    FIND("substring", TableName[ColumnName], 1, 0) > 0
)

<> if All WOs table Work Order Type field contains the word Haul, then include it in the results.
FILTER(
    'All WOs',
    FIND("Haul", 'All WOs'[Work Order Type], 1, 0) > 0
)

Filter on multiple conditions
FILTER(
    'All WOs',
    FIND("Haul", 'All WOs'[Work Order Type], 1, 0) > 0 ||
    'All WOs'[Work Order Number] = 5 ||
    'All WOs'[Status] = "Complete"
)

Using Filter to find multiple entries
FILTER(
    'All WOs',
    'All WOs'[Status] IN {"Complete", "Pending", "Hold"}
)




All WOs Example
Define VAR _Column = SELECTCOLUMNS(
	FILTER(
    'All WOs',
    FIND("Haul", 'All WOs'[Work Order Type], 1, 0) > 0 ||
    'All WOs'[Work Order Type] = "HnI"
	&& ('All WOs'[Status] IN {"Complete", "Pending", "Hold"})
	&& 'All WOs'[Inspection Completed Date]=BLANK()
	),
'All WOs'[Work Order Number],
'All WOs'[Work Order Type],
'All WOs'[Issue Date],
'All WOs'[Applicant Id]
) 
EVALUATE _Column

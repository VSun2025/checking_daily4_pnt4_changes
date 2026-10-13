SELECT 
    [Employee ID],
    [First Name],
    [Last Name],
    [Job Title],
    [Reference ID],
    CONVERT(varchar(10), TRY_CAST([Creation Date] AS DATETIME), 120) AS [Creation Date],
    CONVERT(varchar(10), TRY_CAST([Written Date] AS DATETIME), 120) AS [Written Date],
    CONVERT(varchar(10), TRY_CAST([Final Date] AS DATETIME), 120) AS [Final Date],
    CASE WHEN CHARINDEX('TANKLESS', part_num_contract) > 0 THEN 'NEW TANKLESS' ELSE 'NEW WATER HEATER' END AS Product,
    [Itm Cd],
    SKU,
    '200' AS PymtAmt,
    'ChargedUp Points Payment' AS PymtType,
    '81' AS [Patch Code],
    [SO Ref],
    [Customer Address],
    [Postal Cd],
    0 AS keep
FROM [pbi].[mi_new_wh_weekly_new]
WHERE 
    [Job Title] IN ('Admin. Assistant', 'Billing Operations', 'Business Analyst', 'CCA', 'Charged Up (Non-Access)', 'Claims',
        'Contract Processing', 'District Manager', 'EST', 'Field Manager', 'Finance', 'Home Services Ops', 'Install Clerk', 'Install Planning', 'IT', 'M&L', 'Marketing', 'Ops Support Clerk',
        'Process Analyst', 'Reconciliation', 'Sales Support Clerk', 'Service Clerical', 'Service Clerk', 'Service Planning', 'Super Office Admin', 'Tech Desk', 'Tech Desk Supervisor', 'Workload Planning')
    AND [CSR Workgroup] = 'Sales Support Clerk'
    AND [Employee ID] <> 'SSUPPORT'
    AND CASE WHEN ([Login Name Ref] != CSRId) THEN 1 ELSE 0 END = 1
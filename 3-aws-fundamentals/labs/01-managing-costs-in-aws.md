# Managing costs in AWS
In the search bar of AWS management console, search for "billing". Alternatively, Username -> account details dropdown -> By Billing Dashboard. 

To get more info, click the button "Cost Explorer", which will take you to "AWS Cost Management" page, where you can see current month cost, forecasted month end costs, etc. 

In the left pane, click on "Reports". There you can see Monthly costs by service, etc, for the last 6 mo. 

To identify overrun costs before they occur, use AWS "Budgets". Click it on from the left hand pane. Alternatively, search "Budgets" in the search bar at the top. Create a budget -> Cost budget -> Next -> Period: Monthly; Budget effective date: Recurring budget; Choose how to budget: Fixed; Enter your budgeted amount: 10; Budget name: monthly spend -> Next -> Add an alert threshold -> Next -> Threshold: 80% of budgeted amount; Trigger: Actual/Forecasted; Email recipients: ... -> Next -> Next -> Create budget. 

This is helpful to keep control of any costs. 

You can alo add an Action to a budget, such as when an individual user exceeded their budget, you can add an action to automatically restrict that person/department's permissions to create more resources. 

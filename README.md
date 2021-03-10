# ClientSecurityHash
REF project for the client security hash process in UiPath's Advanced Developer Training. For more information please see the [Process Design Document](https://github.com/ugokcesu/ClientSecurityHash/blob/bad9dd0f1bc68b7b9eeda6681ea8eea9aad17b26/Calculate%20Client%20Security%20Hash%20-%20Process%20Design%20Document.pdf.pdf)

# Dispatcher
Each desired work item is dispatched to a que using **\Dispatcher\Dispatcher.xaml**. 
The dispatcher calls:
- **GatherWorkItems.xaml**: Gathers work items from https://acme-test.uipath.com/work-items
- **AddWorkItemsToQueue.xaml**: Adds each work item that is ```Type==WI5 and Status==Open``` to queue found in **Data\Config.xlsx**

# Performer
Each dispatched queue item contains the work item's ID. The ID is used to gather data, obtain SHA hash and update the item.
The flowchart below shows the handling of each queue item inside process.xaml (the part of RE framework for processing queue items).

![Process flowchart](SHAHashFlowchart.JPG?raw=true "Process flowchart")

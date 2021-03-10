# ClientSecurityHash
REF project for the client security hash process in UiPath's Advanced Developer Training 

# Dispatcher
Each desired work item is dispatched to a que using **\Dispatcher\Dispatcher.xaml**. 
The dispatcher calls:
- **GatherWorkItems.xaml**: Gathers work items from https://acme-test.uipath.com/work-items
- **AddWorkItemsToQueue.xaml**: Adds each work item that is ```Type==WI5 and Status==Open``` to queue found in **Data\Config.xlsx**

# Performer


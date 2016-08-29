#### labuinotetakappios9
######Creating the Xcode project
create a master detail project
######Applying an app icon
shift cmd h ->return to home


######Viewing the template code
```
//executed as expected when the view is loaded, data for the view has loaded up
override func viewDidLoad{
	self.navigationItem.leftBarButtonItem = self.editButtonItem()
let addButton = UIBarButtonItem(barButtonSystemItem: .Add, target:self,action:"insertNew:")
self.navigationItem.rightBarButtonItem=addButton

if let split = self.splitViewController{
	let controllers = split.viewControllers
self.detailViewController = (controllers[controllers.count-1] as! UINavigationController).topViewController as? DetailViewController
}
}
}

//runs before the view is going to apppear on the screen
override func viewWillAppear(animated:Bool){
	self.clearsSelectionOnViewWillAppear=self.splitViewController!.collapsed
super.viewWillAppear(animated)
}

var objects ={AnyObject]()

func insertNew(sender: AnyObject){


	objects.insert(NADate(),atIndex:0)
	let indexPath = NSIndexPath(forRow:0,inSection:0)
	self.tableView.insertRowsAtIndexPaths([indexPath],withAnimation: .Automation)
}
```

# Cronjobs
Easy to use PHP class to create and execute scheduled tasks (cronjobs)
 
##HOW TO USE##
Make a new class like 'Example' which extends \BD\Cronjobs

add a method to your class along with a const name:
```php
const EXAMPLE_METHOD = 'EXAMPLE_METHOD';
public static function example_method() {
		// do some
		return 'done ';
}
```

then in your cron.php file add the task and set the time to execute  
```php
Example::addTask(
		Example::EXAMPLE_METHOD, // the task to run
	 	'10', // every 10th minute
	 	'*',  // every hour
	 	'*/2',  // every 2nd month 
	 	'*',  // every month
	 	'*'  // every day of the week
);
```
And finally run the tasks 
```php
Example::runTasks();
```
Above will return an array where you can see whichs tasks are run 
# the-organizer-app-linux-
organize and search files in high speed and accuracy. can be used entirely via terminal
		
		
		
		hello, here are the flags for both engines! 
		first to add the executables to path so they can be used in terminal at any directory:
			open the app folder and open terminal there
			use this commands: 
				sudo cp organizer /usr/local/bin
				sudo cp searchEngine /usr/local/bin
				
			now executables can be used at any directory and can be called by their name (without the ./ prefix)
			searchEngine search /home/user/Downloads txt file
			
			
		
										THE SEARCH ENGINE FLAGS
										

		1). for normal search: (results that have these keywords)
		
				./searchEngine search /home/user/Downloads keyword1 keyword2 ....
				
				
		2). for date interval search: (returns results between entered date intervals)
		
				./searchEngine search /home/user/Downloads true "20-06-2026" "25-06-2026" keyword1 keyword2 ...
				
		
		3). for universal search: (returns the results of all related files in all folders you organized via the app )
		
				./searchEngine universalSearch keyword0 keyword1...
				
		
		4). for manual indexing for specific folder: (if you suspect a change its better to run this command before search)
		
				./searchEngine validate /home/user/Documents 
		
		
		
		
	
										THE ORGANIZER FLAGS
										
		// the most important flag is the --undo : 
				./organizer /home/user/Downloads --undo
		
										
		1). for organizing by file type (extension) like all png's together ...
			
				./organizer /home/user/Downloads --extOrganizer png
				
		2). for smart organizer (by furequencies of filenames and types and genre and dates ... to unvocer relations in files)
		
				./organizer /home/user/Downloads --smartOrganizer 
				
		3). for organizing by dates (files of same date of creation are together):
				
				./organizer /home/user/Downloads --dateOrganizer
				
		4). for organizing by size (enter 2 interval low and high choose mb or gb)
		
				./organizer /home/user/Downloads --sizeOrganizer mb 10 100
				./organizer /home/user/Downloads --sizeOrganizer gb 1  3
				
		5). for organizing by file genre (for example png, jpeg mp4 are MEDIA , txt doc are DOCUMENT, java,python,sh are CODE...)
		
				./organizer /home/user/Downloads --fileGenre
				
				
				
									THE GROUPERS! bring certain files together by the trait you enter
									
		6). for group by keywords which enables you to override files if they already exist in the destination
		also it allows you to use the OR logic which enables you to bring files that atleast have one keyword
					
					//to group by keywords , this is default it creates a copy if same file exists in destination 
				./organizer /home/user/Downloads --keywordsGrouper keyword1 keyword2....
				
					//to group the files that has all the keywords in their name and override (remove old and bring the new file)
				./organizer /home/user/Downloads --keywordsGrouper true keyword1 keyword2....
				
					//to use or logic 
				./organizer /home/user/Downloads --keywordsGrouper or keyword1 keyword2....
				
					//to use both OR and override modes
				./organizer /home/user/Downloads --keywordsGrouper true or keyword1 keyword2....
				
				
		7). for group by date interval (bring the files that are created between the entered dates)
		
				./organizer /home/user/Downloads --groupByDateInterval "10-06-2026" "30-06-2026"
				
		
		8). for group by specific extension (pack the files that have same type like bring the png's together)
		
				./organizer /home/user/Downloads --packByExt png
			
				./organizer /home/user/Downloads --packByExt true png    //use the override mode 
				
				
		9). for grouping folders together by keywords (for example folders have similar keywords in their names they will be together)
		
				./organizer /home/user/Downloads --folderGrouper keyword1 keyword2....
				
				
					//use or logic (bring folders that have atleast one keyword)
				
				./organizer /home/user/Downloads --folderGrouper or keyword1 keyword2....

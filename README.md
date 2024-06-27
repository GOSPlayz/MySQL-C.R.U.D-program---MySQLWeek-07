1) Add a project
2) List projects
3) Select project
4) Update project
5) Delete a project

1) Add Project
will ask for Project name, Estiamted Hours, Actual Hours, Project Difficulty, Project Notes.
After you fill out the requested information it will create a project on MySQL

2) List Projects
Will list projects ion the MySQL file

3) Select Project
Will ask for a int input used to select the project based on its ID in the MySQL table.

4) Update Project
Can only be used after selecting a project or it will return an error. very similarly to Add project it will ask for all the same fields of information and will change the old info to the newly inputted content respectivly.

5) Delete Project
After selecting Delete project by typing 5 It will ask which project you want to delete based on its int ID in the MySQL table. then it will remove the while project from MySQL.

Technologies used:
Java 17
MySQL

Favorite features:
"1) add project" is one of the features i enjoy the most. It was crucial to the program being useful. Learning how to intake all the different information and save it to MySQL was a really valuable skill to learn. But it wasnt easy, not at first at least. I had some trouble when creating the original questions for the project info. But after some googling and rewatching course videos i was able to understand what i was missing.
```
private void createProject() {
		String projectName = getStringInput("Enter the project name.");
		BigDecimal estimatedHours = getDecimalInput("Enter the estimated hours.");
		BigDecimal actualHours = getDecimalInput("Enter the actualHours.");
		Integer difficulty = getIntInput("Enter the project difficulty (1-5)");
		String notes = getStringInput("Enter the project notes");
		
		Project project = new Project();
		
		project.setProjectName(projectName);
		project.setEstimatedHours(estimatedHours);
		project.setActualHours(actualHours);
		project.setDifficulty(difficulty);
		project.setNotes(notes);
		
		Project dbProject = projectService.addProject(project);
		System.out.println("You have successfully created project: " + dbProject);
	}
```

"3) Select" Is another important tool in this program. It was quite hard to impliment because you need to have the program keep track of a current project. not to mention having another object work off of it means it cant have any errors or else other objects will fail to run.
```
private void selectProject() {
		listProjects();
		Integer projectId = getIntInput("Enter a project ID to select a project");
		
		curProject = null;
		
		curProject = projectService.fetchProjectById(projectId);
		if (Objects.isNull(curProject)) {
			System.out.println("\nThat is not a valid project.");
		}
	}
```

Installation & Usage
You can use this program yourself by downloading the "mysql-java" file and opening it in your eclipse software. and clicking run.

Developers who worked on this project
GOSPlayz

Disclaimer
I will not be updating my git on this program.

Contact Info
Gmail: fleecercowboy@gmail.com
LinkedIn: https://www.linkedin.com/in/gregory-seccomb/



# Sam Eriksen-Schultz

## Projects
<details>
<summary>Lightning</summary>
	<br><a href="https://github.com/SamEriksenSchultz/lightning2">repo link</a>
	<p>
		<br>The goal with this project was to practice applying Math.random() and Processing to create a "lightning storm". <br><br>
		This is the "meat" of this assigment, a method in the Lightning class that generates a random color, path, and stroke for each lightning bolt. 
	
	void init(){ 
    		randColor=new PVector((int)random(0,255),(int)random(0,255),(int)random(0,255));
    		int stroke=int(random(0,10));
		
    		while(y<800){
     			int endX = x + int(random(-4,4));
     			int endY = y + 2;
     			strokeWeight(stroke);
     			stroke(randColor.x,randColor.y,randColor.z); 
     			line(x,y,endX,endY);
     			x = endX;   
     			y = endY;  
    		} 
    
  	}
</p>	
</details>

<details>
<summary>Dice</summary>
	<br><a href="https://github.com/SamEriksenSchultz/dice3">repo link</a><br><br>
	<p>
	The purpose of this project was to practice changing graphics and general code structure. <br><br>
	This was the highlight of my code: using multiple methods, the user can drag and drop the Die object with an offset based on where the Die was clicked. I tried to turn it into a game but I ran into time constraints and it didn't come out the way I had envisioned it. <br><br>
		This first method locks the offset of the user click compared to the coordinates of the Die, and stores it to an x and y float.
	
	void mousePressed() {
  
  	if(overDie) { 
    		locked = true; 
    		fill(255, 255, 255);
  	} else {
    		locked = false;
  	}
  	xOffset = mouseX-location.x; 
  	yOffset = mouseY-location.y;
	
	}
</p>
	<p>
	The second method adjusts the Die location based on the mouse location minus the previously updated offsets.

	void mouseDragged() {
  	
	if(locked) {
    		location.x = mouseX-xOffset; 
    		location.y = mouseY-yOffset; 
  		}
	}
	
</p>
</details>

<details>
<summary>Chemotaxis</summary>
	<br><a href="https://github.com/SamEriksenSchultz/chemotaxis4">repo link</a><br><br>
	<p>
	The purpose of the Chemotaxis project was to practice creativity in problem-solving when presented with a task. In this instance, the task was to create a data structure of "psuedo-AI" that would travel towards a given point.<br><br>
		In order to give the dots "path-finding", I used basic trigonometry and the atan2() method to calculate the hypotenuse between the two given points. This was also excellent practice for working with PVectors instead of individual coordinates.
		
	targetLocation=new PVector(GoalLocation.x,GoalLocation.y);
    float thetaRadians=atan2(targetLocation.y-location.y,targetLocation.x-location.x);
    velocity=new PVector((float)Math.cos(thetaRadians)*4,(float)Math.sin(thetaRadians)*4);
	location.add(velocity);

</p>
</details>

<details>
<summary>Starfield</summary>
	<br><a href="https://github.com/SamEriksenSchultz/starfield5">repo link</a><br><br>
	<p>
		This lab was introduced as a simple way of practicing accessing data from object-based data structures, but I wanted to do something a little more complex. This was my first project using PImages, which were not as intimidating as I had previously thought. This was also my first project using PFont (yay).<br><br>
		My biggest breakthrough from this project was using PImage arrays and delays to create simple animations. While ripping the sprites I also managed to brush up on my GIMP skills. 
		
	void update(){
    		SpaceshipPosition.x+=(d-a)*speed;
    		imageMode(CENTER);
    
    		if(mainTurning){
      			PImage i=mainTurn[(int)currentFrame];
      			image(i,SpaceshipPosition.x,SpaceshipPosition.y,32,32);
      			currentFrame+=0.5;
      			if(currentFrame==turnFrames){
        				currentFrame=0;
        				mainTurning=false;
      			}
    		} else if(!dead){
      			image(mainTurn[0],SpaceshipPosition.x,SpaceshipPosition.y,32,32);
    		} else if(dead && mainExping){
      			PImage i=mainExp[(int)currentFrame];
      			image(i,SpaceshipPosition.x,SpaceshipPosition.y,32,32);
     			currentFrame+=0.1;
      			if((expFrames-currentFrame)<0.1){
        				currentFrame=0;
        				mainExping=false;
      			}
    		}
  	}
</p>
	<br>While this method does in fact, work, I should have split all of the animations into different methods so the code is easier to understand. I did make a conscious effort to use interfaces, inheritance, and organized methods to make my code easier to interpret, but I'm clearly still learning
<br>
</details>
<details>
<summary>Quiz Taker</summary>
	<a href="https://github.com/SamEriksenSchultz/quizTaker">repo link</a>
</details>

## Reflection 
>The main benefit I got from these projects was getting better at managing my projects, from organization to general time management. I learned to better organize my projects to increase my efficiency, and set realistic expectations for myself so I could complete my assignments in a timely manner.

## Development
>This is the most difficult code I've worked on this year. It uses selenium libraries to iterate through potential divs to find a specified quiz, based on a String input earlier in the program. It was difficult using xpath expressions since I had never used them prior to this project. I also had limited quizes to practice on since Dr. R was more concerned about the legal ramifications of creating a quiz taker than my development as a software engineer.

```Java
 boolean searching=true;
 	for(int i=1;searching;i++) {
		try {
		WebElement quiz = driver.findElement(By.xpath("//*[@id=\"course-profile-materials\"]/div[2]/div/div["+i+"]/div/div[3]/div[1]/a"));
		if(quiz.getText().equals(assignName)) {
			searching=false;
			driver.findElement(By.xpath("//*[@id=\"course-profile-materials\"]/div[2]/div/div["+i+"]/div/div[3]/div[1]/a")).click();
			}
		} catch(NoSuchElementException e) {
			searching=false;
			System.out.println("quiz ("+assignName+") not found");
      			driver.quit();
		}
	}
```

## Processes
>When I'm presented with a problem, the first thing I do is plan the structure of the program, without writing it. Once I have an idea of how I want to organize the code, I start planning individual methods. I'll use scratch paper to sketch it out, check the API and look for existing methods that I can use to solve the problem in the most efficient way possible. Once I start writing the actual code, I'll set goals for myself, i.e. finish these 3 methods today, finish this class by the end of the week, etc. When I run into problems, first I'll look for how people with similar problems approached it, and if I can apply it to my program. If that doesn't work, I'll try asking my friends how they would do it, compare solutions, and try to work towards a promise. <br> After working out bugs and ensuring my project meets given requirements, I work on organization and refinement, making the program more efficient, and easier to understand.

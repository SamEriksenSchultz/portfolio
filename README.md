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
		
</p>
</details>
<details>
<summary>Starfield</summary>
	<a href="https://github.com/SamEriksenSchultz/starfield5">repo link</a>
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

# portfolio

* [Lightning](https://github.com/SamEriksenSchultz/lightning2/blob/gh-pages/Lightning.pde)
* [Dice](https://github.com/SamEriksenSchultz/dice3/tree/gh-pages)
* [CHEMOTAXIS](https://github.com/SamEriksenSchultz/chemotaxis4/tree/gh-pages)
* [Starfield](https://github.com/SamEriksenSchultz/starfield5)
* [Quiz Taker](https://github.com/SamEriksenSchultz/starfield5)


This is the most difficult code I've worked on this year. It uses selenium libraries to iterate through potential divs to find a specified quiz, based on a String input earlier in the program.

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
The main benefit I got from these projects was getting better at managing my projects, from organization to general time management. I learned to better organize my projects to increase my efficiency, and set realistic expectations for myself so I could complete my assignments in a timely manner.


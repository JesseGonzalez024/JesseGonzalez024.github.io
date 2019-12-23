---
layout: post
title:      "The office Personality Test"
date:       2019-12-08 21:01:03 -0500
permalink:  the_office_personality_test
---


Greetings & Salutations!

This blog post is in correlation with my CLI Project. The program mirrors a personality test based on the popular tv show: The Office. No doubt, if you've seen the show, more than likely you have a favorite character. Mine happens to be Dwight, because... Battle Star Galactica!

The program presents the user with a series of questions, to which each has 4 answers. The program allows the user to select an answer from the multiple choice and after all questions are successfully answered, the program will return which charming personality do you resemble most. It's meant to both be simple and fun!

#Languages/ Skills/ Tools

* Ruby 2.6.1
* Nokogiri 
* Open-uri
* Pry
* GitHub
* Visual Studio Code

# Getting Started
From the moment I heard the expectations for the project, I knew I wanted to do something worthwhile, that I could seemingly enjoy while working on it. Come to find out, the real thrills would be problem solving through bugs. 

After finding a website with the quiz format I was looking for I began to scrap. Being quite new to this form of treasure hunting, I was required to research additional information and re-read previous lessons. Once the idea sinked in, and after much curiosity splurging through out the Developer Tool, I found the bits and pieces I was looking for. 

Of course finding them and figuring their appropriate CSS Selector are two different things. This is where I truly learned to use Binding.pry

Since then, I double check all of my return values for each line of code before moving on to the next line. I do this simply to add an additional barrier against bugs. I've found that through binding.pry I can also play with potential theories and past references, which in turn saves time.

My first instinct was to store the data I was scraping into Hashes. For a while it worked. But the more layers of data I added the more difficult it made keeping track of said data. 

Also, prior to the project I had been a bit uneasy about OOP. This project completely forced me to break from the safety of the comfortable Hashes I was hiding underneath. Storing data as Objects became joy. 

# The Big One
I faced a number of hurdles and bugs to overcome during this project. The most challenging of them would be preventing invalid entries from the user. At this point the test was bare yet functioning. Yet the program would accept any entry even if it did not follow the rules given to the user. If any entry was unrecognizable or "invalid" my program would easily break or simply not count the question towards the final end result. Given the nature of what the user would be expecting, I could not have this! This bug made my program fragile and easily receptive to errors. 

So the logic & in pseudocode format I wanted to implement was the following:

> Program prints question, program prints answers related to question. Program prompts user for input. Program determines if user's input is acceptable. If user input is not acceptable, program must return the incorrectly answered question and re-prompt the user to answer. Only after user input is valid and question answered can the following question be displayed.
> 

As you can tell from my version of pseudocode, the program would require plenty of conditional and loop statements.

I researched, I asked, I did more research. After many different theories failing, after what felt like scourging the Internet for clues. I attempted to move on to different bugs the program was experiencing.

Previous logic:

```
question_counter = 0
        if Game.all.size <= 35 	            until question_counter == Question.all.size
                while input != 'exit' 	                puts " "
                    @q_count = 0	                puts "##{question_counter + 1}. #{Question.all[question_counter].title}"
                    Question.all.each_with_index do |question, index|	                puts " "
                        puts " "	                @answers = Question.all[question_counter].display_answers
                        puts "##{index + 1}. #{question.title}"	                puts " "
                        puts " "	                user_input = gets.to_i
                        @q_count += 1 	
                        @answers = question.answers.each_with_index do |answer, idx|	                if valid_entry? (user_input)
                            puts "#{idx + 1}. #{answer.title}"	                    counting (user_input)
                            end	                else
                            user_input = gets.strip	                    until valid_entry?(user_input) == true                                                 
                            if valid_entry? (user_input)	                    end    
                                @@all << 1	
                            else	
                             redo_question	
                            end	
                            binding.pry	
                    end	
                end	                end
            puts "Thanks for playing"	                question_counter += 1
        end	            end  
```

It was only during the Project's required 30 min LIVE code session which tasked me with expressing my logic and theories out loud that I came up with a solution.

New Logic:

```
def start_quiz
        question_counter = 0
            until question_counter == Question.all.size
                puts " "
                puts "##{question_counter + 1}. #{Question.all[question_counter].title}"
                puts " "
                @answers = Question.all[question_counter].display_answers
                
                puts " "
                user_input = gets.to_i
                


                if valid? (user_input)
                    true
                else
                    until valid?(user_input) == true                                                 
                        puts " "
                        puts "INVALID ENTRY"
                        puts "Please select a number 1-4"
                        puts " "
                        puts "##{question_counter + 1}. #{Question.all[question_counter].title}"
                        puts " "
                        @answers = Question.all[question_counter].display_answers
                        puts " "
                        user_input = gets.to_i
                        puts " "
                        valid?(user_input)
                    end   
                end
                question_counter += 1
                counting(user_input)
            end  
```

# Don't lose your cool
I learned from seeing others and from self reflecting that panicking was and continues to not be the answer! Every problem, in life, in coding, simply requires research, the right data, and the right attitude. Ever since I began learning to code. My Outlook on problem solving has taken a calmer approach. The results show.

# What's next?
My project is now working the way I want it to. It accounts for user errors without breaking. It completes the test and returns the output it's meant to. The base is there. CLI projects are meant to be minimal. Sometimes that could imply unattractive visuals. That being said, I'd like to add a more visually stimulating return. The website where I did the scraping has shelves of different fun tests. I'd like to refactor the current code so that it could accept different test other than my own. Of course this would imply creating a broader menu, a greater variety of selection. A higher level of Abstraction. But if there's one thing I've learned while working on this project, is that EVERY problem has a solution. 



![](http://blog.aryatra.com/wp-content/uploads/2017/02/Problem-Solving-Albert-Einstein-Quotes.jpghttp://)






# ckad
Here is what I did to pass the exam!

# Todo
* Import the bookmark to your chrome and get comfortable by clicking each section to find relevant code snippets etc.
* Read next section

# Nuggets
## General exam format
* This is a hands on exam on live Kubernetes cluster
* It has 19 questions to solve in 2 hours, so roughly 6.3 minutes per question is all you got
* You are advised to take the exam from a quite place with good internet connection, IMO home is best 
* Join the exam 15 mins before the time
* Keep your identity proof ready and your table clean of unneccessary things

## Time is your enemy
* Ensure you have the best available bandwidth, expect a slight delay/lag on the clusters speacially if you are taking exam from locations like India 
* Set up alias the moment you enter the exam terminal -
  alias k=kubectl
  
* Learn imperative commands 
  For example -
  k get po -A # list all pods in all namespaces
  k run test --image=nginx --restart=Never -- /bin/sh -c env # to run a pod and echo env on stdout
* Get very comfortable navigating the bookmarks that I provided

## Training
https://www.udemy.com/course/certified-kubernetes-application-developer/

## Attempt mock test provided by other contributors
Below is the list in order of my favourites:
* https://github.com/dgkanatsios/CKAD-exercises
* https://github.com/bbachi/CKAD-Practice-Questions

## Gain expertise on basic vi/vim editor commands
* vi to open a file and wq to save and quit
* search text by typimg : followed by line number on esc mode
* copy text section in esc mode and then go to insert mode to paste it in relevant section
* dd in esc mode to delete a line
* u in esc mode to undo the lat edit
* o to insert characters in next line
* i to insert in the same place
* While in insert mode, navigate to front of text by typing '0' and back of text by typing 'e'
* Don't worry about beautifying yaml indentation, you dont get marks for perfact indentation, just make it working

## Question tips and tricks
* The exam tricks you by deliberately asking a question that spans several paragraph
* Always copy and paste text from questions to your termial using copy button provided in the question
* Do not miss the important things like namespace (which may or may not exist)
* Confirm if the questionis asking you to first generate a yaml file at a desired location or directly run the pod/deployment
* Try completing first 10 questions in 50 mins so that you have time to handle big ones
* Always copy and switch to teh correct context before attempting the question, the context is mentioned on the top of every question
* One question could be that create a pod that runs every 22 seconds and prints date, now here you may think that it is cronjob, but you cannot solve using cronjob since it does not support seconds, so the answer is to create a normal pod with following shell script ->
  #!/bin/sh
   while true
   do
    date;
   done; 

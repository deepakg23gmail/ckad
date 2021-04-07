# ckad
Here is what I did to pass the exam!

# First things first
* Import the bookmark to your chrome and get comfortable by clicking each section to find relevant code snippets etc. The file is located with the name kubernetes.io.html in the repo


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
* If you need to delete a pod, then use force flag in order to save time, else deleting pods may take few seconds of your precious time and you will be sitting and waiting at the terminal doing nothing:
  k delete po <podname> --grace-period=0 --force
* Get very comfortable navigating the bookmarks that I provided

## Training
https://www.udemy.com/course/certified-kubernetes-application-developer/

## Attempt mock test provided by other contributors
Below is the list in order of my favourites:
* https://github.com/dgkanatsios/CKAD-exercises
* https://github.com/bbachi/CKAD-Practice-Questions

## Gain expertise on basic vi/vim editor commands
* vi to open a file and 'wq' to save and quit
* search text by typimg : followed by line number on esc mode
* copy text section in esc mode and then go to insert mode to paste it in relevant section
* 'dd' in esc mode to delete a line
* 'u' in esc mode to undo the lat edit
* 'o' to insert characters in next line
* 'i' to insert in the same place
* While in insert mode, navigate to front of text line by typing '0' and end of text line by typing 'e'
* Don't worry about beautifying yaml indentation, you dont get marks for perfact indentation, just make it working

## Question tips and tricks
* The exam tricks you by deliberately asking a question that spans several paragraph
* Always copy and paste text from questions to your termial using copy button provided in the question
* Do not miss the important resources in question like namespace, pods etc. which may or may not exist and accordingly solve
* Confirm if the question is asking you to first generate a yaml file at a desired location or directly run the pod/deployment
* Try completing first 10 questions in 50 mins so that you have time to handle big ones
* Always copy and switch to teh correct context before attempting the question, the context is mentioned on the top of every question
* Where ever possible try to do a quick check to confirm if you solved the question correctly
  For example if you created a NodePort service that exposes a deployment then you can verify quickly by following commands -
  k get po - wide # pod name for the deployment along with its IP Address
  k describe svc <service name> # check if the endpoints are configured with IP Addresses of the pod corresponding to the deployment

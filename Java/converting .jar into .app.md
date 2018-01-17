1. open 'Applications/Other/Automator.app'
2. create new document
3. choose application
4. then choose 'Run applescript'
5. then paste the following code: as an example for Jmol

"
on run {input, parameters}
 set p to POSIX path of (path to me)
 do shell script "java -jar " & p & "/Contents/Java/Jmol.jar"
 
end run
"

6. then save the file in the application folder with desired name as an example 'Jmol.app'
7. open 'Application/Jmol.app/Contents'
8. create a new folder named 'Java'
9. paste .jar file on the 'Java' folder

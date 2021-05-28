# Git Help commands

# Create local repo 

	mkdir developer-cheat-sheets
	cd developer-cheat-sheets
	vim Docker_CheatSheet.md
# init
	cd developer-cheat-sheets
	git init                  // this by default creates 'master' local branch
        git status                // this says branch current is 'master'
        git push                  // as no remote defined, it fails 
# add remote 
	git remote -v             // see which remote , prints nothing first 
	git remote add origin https://github.com/VijayRamisetty/developer-cheat-sheets.git   // add remote with alias origin 
        git remote -v            // now this prints above remote location
# git push
	git push                  // this fails now as no master branch is present in remote origin
        git push -u origin master // push to remote origin , create master if not already present
        git push                  // next time onwards git push is enough to push current selected branch to remote
# git branch
	git branch               // lists local branches
	git branch -r            // lists remote branches
	git branch -a            // lists local + remote branches
# git switch
	git switch <branch-name>   // switch to <branch-name>
	git checkout <branch-name> // this also switch to <branch-name>
# git log
	git log			// prints all commits with code and comment
	git log --oneline       // prints all commits only comment lines
	git log -n 3		// prints last 3 recent commits
# git add
	git add .		// add all untracked files to staged  
	git add <file-name>	// add only selected untracked files  to staged
# git restore  
	git restore --staged <file-name>   // move back from staged to untrack 
# git commit
	git commit -m "commit message"		// commit provided git add is executed earlier
	git commit -a -m "commit message" 	// add & commit in one command

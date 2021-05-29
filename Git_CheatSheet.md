# Git Help commands ( CheatSheet )

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
	git push                  // this fails now as no master branch is present in remote origin (saying no upstream) 
	git push -u origin master // push to remote origin , create master if not already present
	git push                  // next time onwards git push is enough to push current selected branch to remote
	
	git checkout -b feature/branch-1                  // create new from curret in local
	git push					  // fails as no upstream  
	git push --set-upstream origin feature/branch-1   // create a branch in remote/  upstream and allows you to push

# git branch
	git branch               // lists local branches
	git branch -r            // lists remote branches
	git branch -a            // lists local + remote branches
# git switch
	git switch <branch-name>   // switch to <branch-name>
	git checkout <branch-name> // this also switch to <branch-name>
# git checkout
	git checkout <existing-local-branch>		  // selects local existing branch
	git checkout <branch-not-exists>		  // it fails as no such branch
	git checkout -b <branch-not-exits>		  // create new branch from current selected and select the new branch
	
	git checkout -b <new-branch>	  // this will create new-branch from current branch in local
	git checkout -b feature/branch-1  // this will feature create branch from current branch in local
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
	git commit -a -m "commit message" 	// add & commit in one command ( note -a followed by -m )
	git add . ; git commit -m " add details on checkout "   // add and commit in one liner with ; seperated
# git diff
	git diff <branch1> <branch2>
	git diff <master> <dev>     // what in master ++(plusplus) new in dev
	git diff master 	    // assuming your current is dev , what in master ++(plusplus) new in dev
	git diff dev master	    // what in dev show as --(minusminus) not in master 
	git diff origin/dev         // current dev diff with origin/dev , if no changes retuns nothing
# git merge
	git switch master    // here master is our destination
	git merge dev	     // merge changes in dev to current master 
	git merge <src>	     // where dest is current branch
# git fetch
	git fetch	// only fetches metadata from remote + no merge  ( ie example: get from remote dev , won't merge )
# git pull 
	git pull 	// it does git fetch + merge to local  ( ie example: get from remote dev and merge to local dev )
# git delete
	git branch -d <branch-name>              // deletes local branch
	git push origin --delete <branch-name>   // deletes remote branch  -d or --delete
        git push origin -d feature/branch-2      // example to delete remote branch 

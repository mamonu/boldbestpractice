

%%{init: { 'logLevel': 'debug', 'theme': 'base' } }%%
      gitGraph
        commit
        branch MYNEWBRANCH
        checkout MYNEWBRANCH
        commit
        commit
        commit
        checkout main
        merge MYNEWBRANCH

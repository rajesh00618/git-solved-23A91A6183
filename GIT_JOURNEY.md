# My Git Mastery Challenge Journey

## Student Information
- Name: Gurugubelli Rajesh
- Student ID: 23A91A6183
- Repository: https://github.com/rajesh00618/git-solved-23A91A6183
- Date Started: 26-10-2025
- Date Completed: 30-10-2025

## Task Summary
Cloned instructor's repository with pre-built conflicts and resolved all 
merge conflicts across multiple branches using proper Git workflows.

## Commands Used

| Command | Times Used | Purpose |
|---------|------------|----------|
| git clone | 1 | Clone instructor's repository |
| git checkout | 20+ | Switch between branches |
| git branch | 10+ | View and manage branches |
| git merge | 2 | Merge dev and conflict-simulator into main |
| git add | 30+ | Stage resolved conflicts |
| git commit | 15+ | Commit resolved changes |
| git push | 10+ | Push to my repository |
| git fetch | 2 | Fetch updates from instructor |
| git pull | 1 | Pull updates |
| git stash | 2 | Save temporary work |
| git cherry-pick | 1 | Copy specific commit |
| git rebase | 1 | Rebase feature branch |
| git reset | 3 | Undo commits (soft/mixed/hard) |
| git revert | 1 | Safe undo |
| git tag | 2 | Create release tags |
| git status | 50+ | Check repository state |
| git log | 30+ | View history |
| git diff | 20+ | Compare changes |

## Conflicts Resolved

### Merge 1: main + dev (6 files)

#### Conflict 1: config/app-config.yaml
- **Issue**: Production used port 8080, development used 3000
- **Resolution**: Created unified config with environment-based settings
- **Strategy**: Keep production as default, add dev as optional
- **Difficulty**: Medium
- **Time**: 15 minutes

#### Conflict 2: config/database-config.json
- **Issue**: Different database hosts and SSL modes
- **Resolution**: Created separate profiles for production and development
- **Strategy**: Restructured JSON to support both environments
- **Difficulty**: Medium
- **Time**: 10 minutes

#### Conflict 3: scripts/deploy.sh
- **Issue**: Different deployment strategies (production vs docker-compose)
- **Resolution**: Added conditional logic based on DEPLOY_ENV variable
- **Strategy**: Made script handle both environments dynamically
- **Difficulty**: Hard
- **Time**: 20 minutes

#### Conflict 4: scripts/monitor.js
- **Issue**: Different monitoring intervals and log formats
- **Resolution**: Environment-based configuration object
- **Strategy**: Used process.env.NODE_ENV to determine behavior
- **Difficulty**: Medium
- **Time**: 15 minutes

#### Conflict 5: docs/architecture.md
- **Issue**: Different architectural descriptions
- **Resolution**: Merged both descriptions into comprehensive document
- **Strategy**: Created sections for each environment
- **Difficulty**: Easy
- **Time**: 10 minutes

#### Conflict 6: README.md
- **Issue**: Different feature lists and version numbers
- **Resolution**: Combined all features with clear environment labels
- **Strategy**: Organized features by category
- **Difficulty**: Easy
- **Time**: 10 minutes

## Merge 2: main + conflict-simulator (6 files)

### Conflict 1: config/app-config.yaml
- **Issue:** Simulator branch added an extra port and test environment.
- **Resolution:** Added a dedicated `simulator` (or `test`) config section, with clear comments marking it as non-production. Simulator port is present but commented or disabled by default.
- **Strategy:** Main config includes `production` (default), `development`, and a `simulator/test` config block, all separated with clear documentation and comments for safe toggling.
- **Difficulty:** Medium
- **Time:** 10 minutes

### Conflict 2: config/database-config.json
- **Issue:** Simulator used a mock database.
- **Resolution:** Added a `simulator` profile, but `production` remains default, with `simulator` settings clearly marked and not enabled by default. Structured so each environment (production, development, simulator) can be toggled individually.
- **Strategy:** Main JSON has `production`, `development`, and `simulator` keys. Simulator is only used by explicitly setting the environment.
- **Difficulty:** Medium
- **Time:** 10 minutes

### Conflict 3: scripts/deploy.sh
- **Issue:** Simulator introduced new simulated deployment steps.
- **Resolution:** All environments (`production`, `development`, `simulator`) handled with a case/switch logic based on the `DEPLOY_ENV` or a new `--simulate` flag. Experimental steps are only run when simulator env or flag is present, fully documented in code comments.
- **Strategy:** Default logic is always for production. Development and simulator logic are included but separated and only active if explicitly triggered via `DEPLOY_ENV` or `--simulate`.
- **Difficulty:** Hard
- **Time:** 20 minutes

### Conflict 4: scripts/monitor.js
- **Issue:** Conflict between simulated logging/stats and standard logging.
- **Resolution:** Integrated logging config so that simulated statistics and additional metrics are only collected if a `SIMULATOR_MODE` or similar flag is set.
- **Strategy:** Main section is for standard/production logging; experimental/simulated output is wrapped in feature-flag code or marked as comments. Simulator logic never runs unless the flag is on.
- **Difficulty:** Medium
- **Time:** 15 minutes

### Conflict 5: docs/architecture.md
- **Issue:** Simulator branch included special workflow and diagrams.
- **Resolution:** Added a new section titled “Simulation Mode Architecture” after the main and dev workflows. Noted clearly in the doc that “Simulation Mode is for feature testing only; not enabled in production deploys.” All diagrams and workflows are labeled appropriately.
- **Strategy:** Production and development remain the primary documentation; simulation mode is extra and fully documented as non-prod.
- **Difficulty:** Easy
- **Time:** 10 minutes

### Conflict 6: README.md
- **Issue:** New simulator features/version information.
- **Resolution:** Features table reorganized by mode. Simulator features are clearly separated in their own section, and a warning is added that these are experimental/not recommended for production. Versions for each environment are shown separately.
- **Strategy:** Production is first, development second, simulation third with experimental badge/warning.
- **Difficulty:** Easy
- **Time:** 10 minutes


## Most Challenging Parts

1. **Understanding Conflict Markers**: Initially confused by `<<<<<<<`, `=======`, `>>>>>>>` symbols. Learned that HEAD is current branch and the other side is incoming changes.

2. **Deciding What to Keep**: Hardest part was choosing between conflicting code. Learned to read both versions completely before deciding.

3. **Complex Logic Conflicts**: deploy.sh had completely different logic. Had to understand both approaches before combining.

4. **Testing After Resolution**: Making sure resolved code actually worked was crucial.

## Key Learnings

### Technical Skills
- Mastered conflict resolution process
- Understood merge conflict markers
- Learned to use git diff effectively
- Practiced all major Git commands

### Best Practices
- Always read both sides of conflict before resolving
- Test resolved code before committing
- Write detailed merge commit messages
- Use git status frequently
- Commit atomically

### Git Workflow Insights
- Conflicts are normal, not errors
- Take time to understand both changes
- When in doubt, ask for clarification
- Document your resolution strategy
- Keep calm and read carefully

## Reflection
This challenge taught me that merge conflicts aren't scary - they're 
just Git asking "which version do you want?". The key is understanding 
what each side is trying to do before combining them. I now feel 
confident handling conflicts in real projects.

The hands-on practice with all Git commands (especially rebase and 
cherry-pick) was invaluable. I understand the difference between merge 
and rebase, and when to use each. Most importantly, I learned that 
git reflog is a lifesaver!

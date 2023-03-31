# branches-and-tags

A few simple tools for playing with Git branches and tags.

        LICENSE              # MIT License
        README.md            # This README
        define-git-lol       # Convenient alias to show refs and reachable commits 
        git-addfile          # Create, add, and commit files
        git-scratch          # make a scratch repo
        
[Here is a presentation on branches and tags with some exercises.](https://docs.google.com/presentation/d/13yPOoZ7qSulqthG-8fv9Rb4UatTi3TQX2237zOU4q08/edit?usp=sharing)

Descriptions of the three bash scripts follow.

## `define-git-lol`

Define a simple git alias that you can find all over the web.

This script lets you define `git lol` as a global alias (not confined to one project).
The command shows a repository's history, tags, and branches.
The display uses ASCII-graphics, so it's fast and you can use it from the command-line.

You can even ssh into a remote server, and type `git lol`
to look at the structure of a remote repo. 

## `git-addfile`

Add and commit dummy files.

Useful for quickly creating dummy commit history.


### Examples

- `git addfile {a..z}`:
Create 26 files, `a` through `z`, and commit all 26 in a single commit.
- `for filename in file_{1..16}; do git addfile $filename; sleep 1; done`:
Create and commit `file_1` through `file_16`,
all in separate commits, each with a separate timestamp.

Every file has distinct content and a unique commit message, both tied to the filename.

## `git scratch`

Create a simple playground.

### Examples

- `git scratch`: Create a scratch repo, with one, empty, hidden file, `.gitkeep`.

For simple experiments with Git and its hidden, .git directory.

- `git scratch -b`: Create a branched scratch repo with `master` and `davidian` branches,
each with a distinct `README.md` (so the two commits conflict).

For playing with branching, tagging, merging, and rebasing.

- `git scratch -f`: A full system. Create a bare remote, on that "far-away" Git server, `localhost`,
then create two local clones, `itchy`, owned by Itchy Mouse, and `scratchy`, owned by Scratchy Cat.

For exploring the full panoply of Git commits, fetches, pulls, pushes, merges, and so on, by multiple users,
with a single, bare "server" repo for synchronization, and for comparing and contrasting client and server repos.

The `-f` option implies `-b` (the repos are all branched).

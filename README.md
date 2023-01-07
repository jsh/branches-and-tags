# branches-and-tags

This repository has a few simple tools for playing with Git branches and tags.

        LICENSE              # MIT License
        README.md            # This README
        define-git-lol       # Convenient alias to show refs and reachable commits 
        git-addfile          # Create, add, and commit files
        git-scratch          # make a scratch repo
        
[Here is a presentation and some exercises on branches and tags.](https://docs.google.com/presentation/d/13yPOoZ7qSulqthG-8fv9Rb4UatTi3TQX2237zOU4q08/edit?usp=sharing)

Descriptions of the three bash scripts follow.

## `define-git-lol`

Define a simple git alias that you can find all over the web.

This script defines `git lol` as a global alias (not confined to one project),
which shows a repository's history, tags, and branches.
The display uses ASCII-graphics, so it's fast and you can use it from the command-line.

You can even ssh into a remote server, and type `git lol`
to look at the structure of a remote repo. 

## `git-addfile`

Add and commit dummy files.

Useful for quickly creating dummy commit history.


### Examples

- `git addfile {a..z}`: Create 26 files, `a` through `z`,
and commit all 26 in a single commit.
- `for $file in file_{1..16}; do git addfile $file; sleep 1; done`:
Create and commit `file_1` through `file_16`,
all in separate commits, each with a separate timestamp.

Every file has distinct content and a unique commit message tied to the filename.

## `git scratch`

Create a simple playground.

### Examples

- `git scratch`: Create a scratch repo, with one, empty, hidden file, `.gitkeep`.

Useful for simple questions about Git.
- `git scratch -b`: Create a branched scratch repo with `master` and `davidian` branches,
each with a distinct `README.md` (so the two commits conflict).

Useful for questions about branching, tagging, and merging.
- `git scratch -r: Create a repo with a bare remote, on that "far-away" Git server, `localhost`,
then make with two local clones, `itchy`, owned by Itchy Mouse, and `scratchy`, owned by Scratchy Cat.

Useful for exploring the full interaction of Git commits, fetches, pulls, pushes, merges, and so on, by multiple users,
with a single, bare "server" repo for synchronization.

The `-r` option implies `-b` (the repos are all branched).

I am a logger of commits in a repository. I follow the builder pattern in that I take several parameters (author, sha/branch, path, since, until) to build an object (an array of commits).

My responsibility is to build up the query parameters and execute it on the repository

My collaborator is GHRepository.

Public API and Key Messages

- author: all commits committed by author (can be email or login name)
- inPath: all commits which created/deleted/modified the given path.
- since and until: All commits from and to the given dates.

I am created on a repository by sending commitLogger to a GHRepository, or by sending on: aGHRepository to my class.

Internal Representation and Key Implementation Points.

    Instance Variables
	parameters:		The query parameters. (Dictionary)
	repo:			The repository to search on. (GHRepository)
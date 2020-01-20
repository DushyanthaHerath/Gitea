# Gitea API Client

This package provides an API client for [Gitea](https://gitea.io) API Version 1.

*Caution! This package is still under development*

## Getting Started

### Prerequisites

This package has the following requirements:

* PHP 7.2

### Installing

Install latest version via composer:

```
composer require avency/gitea
```

### Basic usage

```
// This file is generated by Composer
require_once __DIR__ . '/vendor/autoload.php';

// - - - - -

// Create client and authenticate
$giteaClient = new Avency\Gitea\Client(
    'https://gitea.yourdomain.com',
    [
        'type' => Avency\Gitea::AUTH_TOKEN,
        'auth' => 'your-auth-token'
    ]
);

or

$giteaClient = new Avency\Gitea\Client(
    'https://gitea.yourdomain.com',
    [
        'type' => Avency\Gitea::AUTH_BASIC_AUTH,
        'auth' => [
            'username' => 'your-username',
            'password' => 'your-password',
        ]
    ]
);

// - - - - -

// Get a single repository
$repository = $giteaClient->repositories()->get('owner', 'repoName');

// Get version
$repository = $giteaClient->miscellaneous()->version();
```

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available,
see the [tags on this repository](https://github.com/avency/gitea/contributors).

## Authors

* Michael Gerdemann - [avency GmbH](https://www.avency.de)

See also the list of [contributors](https://github.com/avency/gitea/graphs/contributors) who
participated in this project.

## License

This project is licensed under the MIT License - see the
[LICENSE.md](https://github.com/avency/gitea//blob/master/LICENSE.md) file for details

## Status of endpoints

#### Admin

Status | Method | Endpoint
--- | --- | ---
❌ | GET | /admin/orgs
❌ | POST | /admin/users
❌ | DELETE | /admin/users/{username}
❌ | PATCH | /admin/users/{username}
❌ | POST | /admin/users/{username}/keys
❌ | DELETE | /admin/users/{username}/keys/{id}
❌ | POST | /admin/users/{username}/orgs
❌ | POST | /admin/users/{username}/repos

#### Miscellaneous

Status | Method | Endpoint
--- | --- | ---
✅ | POST | /markdown
✅ | POST | /markdown/raw
✅ | GET | /signing-key.gpg
✅ | GET | /version

#### Organization

Status | Method | Endpoint
--- | --- | ---
❌ | POST | /org/{org}/repos
❌ | POST | /orgs
❌ | GET | /orgs/{org}
❌ | DELETE | /orgs/{org}
❌ | PATCH | /orgs/{org}
❌ | GET | /orgs/{org}/hooks
❌ | POST | /orgs/{org}/hooks/
❌ | GET | /orgs/{org}/hooks/{id}
❌ | DELETE | /orgs/{org}/hooks/{id}
❌ | PATCH | /orgs/{org}/hooks/{id}
❌ | GET | /orgs/{org}/members
❌ | GET | /orgs/{org}/members/{username}
❌ | DELETE | /orgs/{org}/members/{username}
❌ | GET | /orgs/{org}/public_members
❌ | GET | /orgs/{org}/public_members/{username}
❌ | PUT | /orgs/{org}/public_members/{username}
❌ | DELETE | /orgs/{org}/public_members/{username}
❌ | GET | /orgs/{org}/repos
❌ | GET | /orgs/{org}/teams
❌ | POST | /orgs/{org}/teams
❌ | GET | /orgs/{org}/teams/search
❌ | GET | /teams/{id}
❌ | DELETE | /teams/{id}
❌ | PATCH | /teams/{id}
❌ | GET | /teams/{id}/members
❌ | GET | /teams/{id}/members/{username}
❌ | PUT | /teams/{id}/members/{username}
❌ | DELETE | /teams/{id}/members/{username}
❌ | GET | /teams/{id}/repos
❌ | PUT | /teams/{id}/repos/{org}/{repo}
❌ | DELETE | /teams/{id}/repos/{org}/{repo}
❌ | GET | /user/orgs
❌ | GET | /users/{username}/orgs

#### Issue

Status | Method | Endpoint
--- | --- | ---
❌ | GET | /repos/issues/search
❌ | GET | /repos/{owner}/{repo}/issues
❌ | POST | /repos/{owner}/{repo}/issues
❌ | GET | /repos/{owner}/{repo}/issues/comments
❌ | DELETE | /repos/{owner}/{repo}/issues/comments/{id}
❌ | PATCH | /repos/{owner}/{repo}/issues/comments/{id}
❌ | GET | /repos/{owner}/{repo}/issues/comments/{id}/reactions
❌ | POST | /repos/{owner}/{repo}/issues/comments/{id}/reactions
❌ | DELETE | /repos/{owner}/{repo}/issues/comments/{id}/reactions
❌ | GET | /repos/{owner}/{repo}/issues/{index}
❌ | PATCH | /repos/{owner}/{repo}/issues/{index}
❌ | GET | /repos/{owner}/{repo}/issues/{index}/comments
❌ | POST | /repos/{owner}/{repo}/issues/{index}/comments
❌ | POST | /repos/{owner}/{repo}/issues/{index}/deadline
❌ | GET | /repos/{owner}/{repo}/issues/{index}/labels
❌ | PUT | /repos/{owner}/{repo}/issues/{index}/labels
❌ | POST | /repos/{owner}/{repo}/issues/{index}/labels
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/labels
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/labels/{id}
❌ | GET | /repos/{owner}/{repo}/issues/{index}/reactions
❌ | POST | /repos/{owner}/{repo}/issues/{index}/reactions
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/reactions
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/stopwatch/delete
❌ | POST | /repos/{owner}/{repo}/issues/{index}/stopwatch/start
❌ | POST | /repos/{owner}/{repo}/issues/{index}/stopwatch/stop
❌ | GET | /repos/{owner}/{repo}/issues/{index}/subscriptions
❌ | PUT | /repos/{owner}/{repo}/issues/{index}/subscriptions/{user}
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/subscriptions/{user}
❌ | GET | /repos/{owner}/{repo}/issues/{index}/times
❌ | POST | /repos/{owner}/{repo}/issues/{index}/times
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/times
❌ | DELETE | /repos/{owner}/{repo}/issues/{index}/times/{id}
❌ | GET | /repos/{owner}/{repo}/labels
❌ | POST | /repos/{owner}/{repo}/labels
❌ | GET | /repos/{owner}/{repo}/labels/{id}
❌ | DELETE | /repos/{owner}/{repo}/labels/{id}
❌ | PATCH | /repos/{owner}/{repo}/labels/{id}
❌ | GET | /repos/{owner}/{repo}/milestones
❌ | POST | /repos/{owner}/{repo}/milestones
❌ | GET | /repos/{owner}/{repo}/milestones/{id}
❌ | DELETE | /repos/{owner}/{repo}/milestones/{id}
❌ | PATCH | /repos/{owner}/{repo}/milestones/{id}

#### Repository

Status | Method | Endpoint
--- | --- | ---
✅ | POST | /repos/migrate
✅ | GET | /repos/search
✅ | GET | /repos/{owner}/{repo}
✅ | DELETE | /repos/{owner}/{repo}
✅ | PATCH | /repos/{owner}/{repo}
❌ | GET | /repos/{owner}/{repo}/archive/{archive}
❌ | GET | /repos/{owner}/{repo}/branches
❌ | GET | /repos/{owner}/{repo}/branches/{branch}
❌ | GET | /repos/{owner}/{repo}/collaborators
❌ | GET | /repos/{owner}/{repo}/collaborators/{collaborator}
❌ | PUT | /repos/{owner}/{repo}/collaborators/{collaborator}
❌ | DELETE | /repos/{owner}/{repo}/collaborators/{collaborator}
❌ | GET | /repos/{owner}/{repo}/commits
❌ | GET | /repos/{owner}/{repo}/commits/{ref}/statuses
❌ | GET | /repos/{owner}/{repo}/contents
❌ | GET | /repos/{owner}/{repo}/contents/{filepath}
❌ | PUT | /repos/{owner}/{repo}/contents/{filepath}
❌ | POST | /repos/{owner}/{repo}/contents/{filepath}
❌ | DELETE | /repos/{owner}/{repo}/contents/{filepath}
❌ | GET | /repos/{owner}/{repo}/editorconfig/{filepath}
❌ | GET | /repos/{owner}/{repo}/forks
❌ | POST | /repos/{owner}/{repo}/forks
❌ | GET | /repos/{owner}/{repo}/git/blobs/{sha}
❌ | GET | /repos/{owner}/{repo}/git/commits/{sha}
❌ | GET | /repos/{owner}/{repo}/git/refs
❌ | GET | /repos/{owner}/{repo}/git/refs/{ref}
❌ | GET | /repos/{owner}/{repo}/git/tags/{sha}
❌ | GET | /repos/{owner}/{repo}/git/trees/{sha}
❌ | GET | /repos/{owner}/{repo}/hooks
❌ | POST | /repos/{owner}/{repo}/hooks
❌ | GET | /repos/{owner}/{repo}/hooks/git
❌ | GET | /repos/{owner}/{repo}/hooks/git/{id}
❌ | DELETE | /repos/{owner}/{repo}/hooks/git/{id}
❌ | PATCH | /repos/{owner}/{repo}/hooks/git/{id}
❌ | GET | /repos/{owner}/{repo}/hooks/{id}
❌ | DELETE | /repos/{owner}/{repo}/hooks/{id}
❌ | PATCH | /repos/{owner}/{repo}/hooks/{id}
❌ | POST | /repos/{owner}/{repo}/hooks/{id}/tests
❌ | GET | /repos/{owner}/{repo}/keys
❌ | POST | /repos/{owner}/{repo}/keys
❌ | GET | /repos/{owner}/{repo}/keys/{id}
❌ | DELETE | /repos/{owner}/{repo}/keys/{id}
❌ | POST | /repos/{owner}/{repo}/mirror-sync
❌ | GET | /repos/{owner}/{repo}/pulls
❌ | POST | /repos/{owner}/{repo}/pulls
❌ | GET | /repos/{owner}/{repo}/pulls/{index}
❌ | PATCH | /repos/{owner}/{repo}/pulls/{index}
❌ | GET | /repos/{owner}/{repo}/pulls/{index}/merge
❌ | POST | /repos/{owner}/{repo}/pulls/{index}/merge
❌ | GET | /repos/{owner}/{repo}/raw/{filepath}
❌ | GET | /repos/{owner}/{repo}/releases
❌ | POST | /repos/{owner}/{repo}/releases
❌ | GET | /repos/{owner}/{repo}/releases/{id}
❌ | DELETE | /repos/{owner}/{repo}/releases/{id}
❌ | PATCH | /repos/{owner}/{repo}/releases/{id}
❌ | GET | /repos/{owner}/{repo}/releases/{id}/assets
❌ | POST | /repos/{owner}/{repo}/releases/{id}/assets
❌ | GET | /repos/{owner}/{repo}/releases/{id}/assets/{attachment_id}
❌ | DELETE | /repos/{owner}/{repo}/releases/{id}/assets/{attachment_id}
❌ | PATCH | /repos/{owner}/{repo}/releases/{id}/assets/{attachment_id}
❌ | GET | /repos/{owner}/{repo}/signing-key.gpg
❌ | GET | /repos/{owner}/{repo}/stargazers
❌ | GET | /repos/{owner}/{repo}/statuses/{sha}
❌ | POST | /repos/{owner}/{repo}/statuses/{sha}
❌ | GET | /repos/{owner}/{repo}/subscribers
❌ | GET | /repos/{owner}/{repo}/subscription
❌ | PUT | /repos/{owner}/{repo}/subscription
❌ | DELETE | /repos/{owner}/{repo}/subscription
❌ | GET | /repos/{owner}/{repo}/tags
❌ | GET | /repos/{owner}/{repo}/times
❌ | GET | /repos/{owner}/{repo}/topics
❌ | PUT | /repos/{owner}/{repo}/topics
❌ | PUT | /repos/{owner}/{repo}/topics/{topic}
❌ | DELETE | /repos/{owner}/{repo}/topics/{topic}
❌ | GET | /repositories/{id}
❌ | GET | /topics/search
❌ | POST | /user/repos

#### User

Status | Method | Endpoint
--- | --- | ---
❌ | GET | /repos/{owner}/{repo}/times/{user}
❌ | GET | /user
❌ | GET | /user/emails
❌ | POST | /user/emails
❌ | DELETE | /user/emails
❌ | GET | /user/followers
❌ | GET | /user/following
❌ | GET | /user/following/{username}
❌ | PUT | /user/following/{username}
❌ | DELETE | /user/following/{username}
❌ | GET | /user/gpg_keys
❌ | POST | /user/gpg_keys
❌ | GET | /user/gpg_keys/{id}
❌ | DELETE | /user/gpg_keys/{id}
❌ | GET | /user/keys
❌ | POST | /user/keys
❌ | GET | /user/keys/{id}
❌ | DELETE | /user/keys/{id}
❌ | GET | /user/repos
❌ | POST | /user/repos
❌ | GET | /user/starred
❌ | GET | /user/starred/{owner}/{repo}
❌ | PUT | /user/starred/{owner}/{repo}
❌ | DELETE | /user/starred/{owner}/{repo}
❌ | GET | /user/stopwatches
❌ | GET | /user/subscriptions
❌ | GET | /user/teams
❌ | GET | /user/times
❌ | GET | /users/search
❌ | GET | /users/{follower}/following/{followee}
❌ | GET | /users/{username}
❌ | GET | /users/{username}/followers
❌ | GET | /users/{username}/following
❌ | GET | /users/{username}/gpg_keys
❌ | GET | /users/{username}/heatmap
❌ | GET | /users/{username}/keys
❌ | GET | /users/{username}/repos
❌ | GET | /users/{username}/starred
❌ | GET | /users/{username}/subscriptions
❌ | GET | /users/{username}/tokens
❌ | POST | /users/{username}/tokens
❌ | DELETE | /users/{username}/tokens/{token}

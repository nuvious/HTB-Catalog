# Hack the Box (HTB) Catalog in JSON

I like many HTB users will do write-ups of the challenges I complete to get
practice with doing formal write-ups in the cybersecurity space and to provide
some practical evidence of skill for job searches and other activities.

This repository contains a machine-readable catalog of all the HTB machines,
challenges, and sherlocks in their catalog. This allows me to quickly sort
through the list of challenges and machines to find ones that have recently
retired so I can take write-ups in github repositories and gists and make them
public.

This repository will only contain the raw json and implementation details will
be kept separate. Collecting this information requires authorization so I can't
turn this into a github action without some significant engineering, so I'll try
to update these periodically. May try to automate this in the future but this
is the ammount of effort I can afford at the moment.

If the repository falls significantly out of date feel free to open up an issue
to get my attention. I have enough reason to keep this populated for my own
interests and will try to keep it up to date as best I can.

## Note to HTB

If this repository is for any reason inappropriate or against your TOS, please
open up an issue requesting the repository's removal.

## Schema

### Machines

Machines have two different api endpoints so I divided them into two files. If
you pull them all in at once you can still distinguish retired vs active by the
`free` value which is either `true` or `false` for active vs retired machines
_generally_. There are a few machines which are retired that are free but
that's usually on the order of single-digits.

#### Example Machine

```json
[
 ...
 {
  "id": 589,
  "avatar": "/storage/avatars/e809e8df8d66ec8bb2ca3bbcc1942de7.png",
  "name": "Jab",
  "static_points": 30,
  "sp_flag": 0,
  "os": "Windows",
  "points": 30,
  "star": 4.5,
  "release": "2024-02-24T19:00:00.000000Z",
  "easy_month": 0,
  "poweroff": 0,
  "free": true,
  "difficulty": 51,
  "difficultyText": "Medium",
  "user_owns_count": 2722,
  "authUserInUserOwns": false,
  "root_owns_count": 2492,
  "authUserHasReviewed": false,
  "authUserInRootOwns": false,
  "isTodo": false,
  "is_competitive": false,
  "active": null,
  "feedbackForChart": {
   "counterCake": 89,
   "counterVeryEasy": 82,
   "counterEasy": 353,
   "counterTooEasy": 595,
   "counterMedium": 1045,
   "counterBitHard": 653,
   "counterHard": 432,
   "counterTooHard": 106,
   "counterExHard": 34,
   "counterBrainFuck": 55
  },
  "ip": null,
  "playInfo": {
   "isActive": null,
   "expires_at": null
  },
  "labels": [],
  "recommended": 0
 },
 {
  "id": 588,
  "avatar": "/storage/avatars/2cdef06b99725f3dcce38431a95b7b77.png",
  "name": "Office",
  "static_points": 40,
  "sp_flag": 0,
  "os": "Windows",
  "points": 0,
  "star": 4.7,
  "release": "2024-02-17T19:00:00.000000Z",
  "easy_month": 0,
  "poweroff": 0,
  "free": true,
  "difficulty": 64,
  "difficultyText": "Hard",
  "user_owns_count": 2023,
  "authUserInUserOwns": false,
  "root_owns_count": 1634,
  "authUserHasReviewed": false,
  "authUserInRootOwns": false,
  "isTodo": false,
  "is_competitive": false,
  "active": null,
  "feedbackForChart": {
   "counterCake": 50,
   "counterVeryEasy": 21,
   "counterEasy": 93,
   "counterTooEasy": 185,
   "counterMedium": 360,
   "counterBitHard": 444,
   "counterHard": 709,
   "counterTooHard": 371,
   "counterExHard": 114,
   "counterBrainFuck": 109
  },
  "ip": null,
  "playInfo": {
   "isActive": null,
   "expires_at": null
  },
  "labels": [],
  "recommended": 0
 }
 ...
]
```

### Challenges and Sherlocks

Challenges and Sherlocks have a value `state` that is either `retired` or `active`:

#### Example Challenge

```json
[
 ...
 {
  "id": 706,
  "name": "Regularity",
  "difficulty": "Very Easy",
  "user_difficulty": "2.53",
  "difficulty_chart": {
   "counterCake": 14,
   "counterVeryEasy": 20,
   "counterEasy": 14,
   "counterTooEasy": 5,
   "counterMedium": 3,
   "counterBitHard": 1,
   "counterHard": 0,
   "counterTooHard": 0,
   "counterExHard": 0,
   "counterBrainFuck": 1
  },
  "state": "retired",
  "category_id": 4,
  "category_name": "Pwn",
  "solves": 61,
  "is_owned": false,
  "rating": null,
  "rating_count": 0,
  "auth_user_has_reviewed": false,
  "avatar": null,
  "release_date": "2024-06-07T20:00:00.000000Z"
 }
 ...
]
```

#### Example Sherlock

```json
 {
  "id": 572,
  "name": "Constellation",
  "difficulty": "Medium",
  "state": "retired",
  "category_id": 19,
  "category_name": "Threat Intelligence",
  "solves": 426,
  "is_owned": false,
  "rating": 4.5,
  "rating_count": 30,
  "auth_user_has_reviewed": false,
  "progress": 0,
  "avatar": "https://labs.hackthebox.com/storage/challenges/e6b4b2a746ed40e1af829d1fa82daa10.png",
  "release_date": "2023-12-14T19:00:00.000000Z"
 },
```

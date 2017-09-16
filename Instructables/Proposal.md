# Full-stack Proposal Preparation

-----
## Instructables Component Hierarchy

### General
- `App`
  - `Navbar`
  - `MainPage` (all other Components are rendered inside here)
  - `Footer`

-----

## State Shape
```js
{
  entities: {
    projects: {
      1: {
        id: 1,
        title: 'Project1',
        user_id: 1,
        img: 'assets/...',
        body: 'Body1'
      },
      2: {
        id: 2,
        user_id: 2,
        title: 'Project2',
        img: 'assets/...',
        body: 'Body2'
      },
      3: {
        id: 3,
        user_id: 3,
        title: 'Project3',
        img: 'assets/...',
        body: 'Body3'
      }
    },

    users: {
      1: {
       id: 1,
       username: "Cat1",
       img_url: "..."
      },
      2: {
       id: 2,
       username: "Cat2",
       img_url: "..."
      },
      3: {
       id: 3,
       username: "Cat3",
       img_url: "..."
      }
    }
  },

  ui: {
   loading: true/false
  },

  session: {
    id: 2,
    username: "cat2",
    img_url: "..."
  }

}

```


------
## Schema

- **User**
  - username t.string
  - email t.string

  - password t.string
  - password_digest
  - session_token
  - has_many :projects
  - has_many :comments

- **Project**
  - title t.string
  - image_url t.string
  - published true, false

  - user_id t.integer
  - belong_to :user
  - has_many :steps

  - has_many :comments

- **Step**
  - title t.string
  - description t.text // libaray stylely text editor ju

  - video_url t.string ???
  - project_id t.integer
  - belong_to :project

- **Comment**
  - body t.string
  - user_id
  - project_id

  - belong_to :user
  - belong_to :project

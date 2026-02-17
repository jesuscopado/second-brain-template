---
obsidianUIMode: preview
---

Your launchpad. Your home base. This is **home**.

> [!abstract]- # Atoms
> > *Where would you like to go?*
>
> - **Maps**: [[AI]] · [[Books]] · [[Films]]
> - **Atoms**: `Atoms/Things/` · `Atoms/People/` · `Atoms/Sources/`
>
> To capture something quickly, drop it in your **inbox**: `+/`

> [!example]- # Calendar
> > *What's on your mind?*
>
> - To do your daily check-in → `/daily`
> - To see logs and decisions → `Calendar/Logs/`
>
> > [!todo]+ ### Pending tasks
> > ```tasks
> > not done
> > limit 10
> > ```

> [!rocket]- # Projects
> > *What are you working on?*
>
> > [!success]+ ### 🔥 On
> > ```dataview
> > TABLE WITHOUT ID
> > file.link as "",
> > rank as "Rank"
> > FROM "Projects/On"
> > SORT rank desc
> > ```
>
> > [!tip]+ ### ♻️ Ongoing
> > ```dataview
> > TABLE WITHOUT ID
> > file.link as "",
> > rank as "Rank"
> > FROM "Projects/Ongoing"
> > SORT rank desc
> > ```
>
> > [!warning]- ### 〰️ Simmering
> > ```dataview
> > TABLE WITHOUT ID
> > file.link as "",
> > rank as "Rank"
> > FROM "Projects/Simmering"
> > SORT rank desc
> > ```
>
> > [!quote]- ### 💤 Sleeping
> > ```dataview
> > TABLE WITHOUT ID
> > file.link as "",
> > rank as "Rank"
> > FROM "Projects/Sleeping"
> > SORT rank desc
> > ```

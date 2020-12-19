---
layout: post
title:      "The Home stretch"
date:       2020-12-19 00:58:00 +0000
permalink:  the_home_stretch
---


Well, this is it. My final project.

Its...weird to be finishing everything up.

It took me about 3 or 4 days to land on a project idea for React and in the end it all came down to me thinking that it would be nice to have an app to keep track of all my project ideas in one place and track them as i worked. Hence, App Sketchbook was born.

Despite losing our dear leader Alex to a new job and thus this whole unit feeling weirdly light, I didnt seem to have a whole lot trouble with any one thing like i have in the past. With one exception, figuring out state for my project edit forms. THAT took some doing and some solid team effort, the better part of a day...and me realizing I was returning a plural word instead of a singular one inside my mapStateToProps. 

This:

```
const mapStateToProps = ({ projects }, props) => {
    const projectId = +props.match.params.id;
    const project = projects.all.filter(p =>
     p.id === projectId
    );
    return {
      projects: project
      };
    };
```

became this:

```
const mapStateToProps = ({ projects }, props) => {
    const projectId = +props.match.params.id;
    const project = projects.all.filter(p =>
     p.id === projectId
    );
    return {
      project
      };
    };
```

amazing what an s can do...and an afternoon.

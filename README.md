Analyzing 30 Rock Data
================
Phillip Sanderell

“Science is my most favorite subject, especially the Old Testament.”
Continuing my one-show streak of analyzing data for my favorite
television shows, I have chosen to explore Tina Fey’s *30 Rock*. In this
post I look forward to learning about what it takes to make a truly
fantastic show, and perhaps impress my friends from The Second City.

# Exploring episode metadata

## IMDb rating

IMDb ratings tend to be my go-to metric for scoring episodes, and
something that I find particularly interesting. The plot below shows the
distribution of IMDb ratings for every regular-season episode of the
show.

![](README_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

The ratings do seem to have an approximately normal distribution
centered at eight stars. Something worth noting is that while IMDb
ratings range from 0 to 10, I find episode ratings for various shows
hover around 8 starts—perhaps there is some psychological reason for
that, but unfortunately we have no way of knowing, medicine is not a
science.

The plot above is useful for examining episode ratings overall, but it
is easy to tell if certain seasons rate better than others. The next
plot was made in an effort to make this more clear. Each dot represents
an episode going in order of air date from left to right, colored by
season, and sized by number of IMDb votes. The “notched” box plots show
the 25th, 50th, and 75th percentiles of ratings for each season—if the
notches in different season’s boxes don’t overlap, it suggests the
medians are significantly different.

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

Based on the notched box plots, season six had a significantly lower
median rating than seasons two and three—perhaps that explains why
season seven is the last with only 12 episodes. NBC is quick to cancel
non-cop shows when they’re not doing well.

## Prevalence of writers

The plot below lists every writer of the show in order of total episodes
written for the series. The median IMDb rating for each writer’s
episodes is listed beside their name. Please note, on the full cast and
crew page for each episode, IMDb lists some people in the writing
credits section as ‘story editor’, ‘executive story editor’, etc., and
it always lists Tina Fey as ‘created by’. The counts in the plot below
only capture a writer if they are listed as ‘written by’.

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Tina Fey clearly did not sleep, having had the highest number of
episodes written (or tied for) in five out of seven seasons, all while
staring in every episode. Robert Carlock wrote the second most total
episodes for the show, which is fortunate because I love his writing
style: quick, ridiculous, and too witty to keep up with sometimes. Tina
Fey and Robert Carlock went on to co-create *The Unbreakable Kimmy
Schmidt* (which would be another interesting show to analyze) bringing
along a lot of 30 Rock writing alumna. Tracy Wigfield created the NBC
series *Great News*, another great watch. I believe Donald Glover is
credited as a story consultant writer on some episodes that do not show
up here, but looks like he worked on the actual script for two episodes.

### Did bringing on more writers cause the ratings downfall?

It’s a leading question, I know, but it is curious to see that 30 Rock’s
ratings started going downhill in season four and that happens to also
be the season that the main writing staff added about four new writers.

I think a way to answer this question simply is to compare the
distribution of ratings in the fourth through seventh seasons between
the original writing team and the new writers (excluding guest writers).
If they have similar distributions we cannot make any conclusions about
the new writers, if the new writers have lower ratings then we can
reasonably assume they did not do the show any favors.

For the purposes of this question, I define the original writing team
as:

-   Tina Fey

-   Robert Carlock

-   Jack Burditt

-   Matt Hubbard

-   Kay Cannon

-   Ron Weiner

-   John Riggi

The new writers are:

-   Tracey Wigfield

-   Josh Siegal

-   Dylan Morgan

-   Vali Chandrasekaran

-   Tom Ceraulo

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

From season four and on, the episodes written by the new writers had
lower median IMDb ratings than the original writing team. This evidence
gives some merit to my hypothesis but with only 137 aired episodes, I
don’t think there is enough data to be certain the new writers are all
worse. If every writer wrote many more episodes, perhaps we could look
at each writer’s episode ratings individually—there could be some
original writing team members that produce consistently lower ratings
and some new writers that produce consistently higher ratings.

## Prevalence of directors

The plot below lists every director of the show in order of total
episodes directed for the series. The median IMDb rating for episodes
directed by each person is listed beside their name.

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

I wonder what happened to Adam Bernstein? He directed just as much as
Don Scardino in season one and then didn’t direct anymore. Jeff Richmond
directed a number of later episodes, avid watchers may recognize his
name as the composer for the series (or as Tina Fey’s husband in real
life). I notice Robert Carlock, the second-most credited writer,
directed an episode in the final season—I wonder if there is any other
writer/director overlap.

# Examining characters listed in episode description

Do episodes with Cerie in the spotlight score higher than those with
Frank? Can we find any relationship with character names and IMDb
ratings?

## A little more web scraping needs performed to gather a list of character names

This Github repo includes the original Web Scraping code used to gather
this data. You can view the README.Rmd file in this repo to see the
extra web scraping code used to gather character names.

## Plotting character rating prevalence

I’m interested in seeing if certain characters being the main focus of
an episode drives the IMDb rating up or down. Unfortunately a large
assumption needs to be made: characters being the main focus of an
episode are listed in the episode description on IMDb. Of course I’m
sure this assumption is not perfect, there are certainly episode
descriptions that don’t mention characters with prominent story lines in
the episode.

The plot below shows the top 30 or so characters listed in episode
descriptions, with their 25th, 50th, and 75th percentiles of episode
ratings given on the left bar, dot, and right bar of each row. The
larger the dot, the more episodes with that character mentioned in the
description—the top 5 characters are highlighted.

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

I’m not surprised Dr. Spaceman is stably near the top of the list. Of
the main characters there doesn’t seem to be a difference in the
distribution of episode ratings. However, I do notice annecdotally that
a lot of episodes with characters often associated with Jack (romantic
partners or business associates) outpace characters associated with Liz
(mostly romantic partners).

| Characters associated with Jack | Characters associated with Liz |
|---------------------------------|--------------------------------|
| Hank                            | Dr. Baird                      |
| Elisa                           | Floyd                          |
| Nancy                           | Criss                          |
| Avery                           | Dennis                         |
| Devon                           |                                |
| Don                             |                                |

# Conclusion

This analysis has opened my eyes to the dichotomy of ratings between
seasons and the potential factors driving those. I’ve gained a new
appreciation for episodes written by Tina Fey and ones including
characters focusing on Jack. If you’re a fellow fan of 30 Rock, feel
free to reach out—I’d love to chat!

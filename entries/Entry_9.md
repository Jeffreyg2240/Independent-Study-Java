### Week 9:

On the final week, we invested our time in polishing the project. Johnson was able to add a home screen and used the sound files I found from week 6. I randomized the song files so it could the game could have a hint of anticipation. In addition to this, we worked on the bomb, I started with the bomb class. Thus far I’ve made it so that only one bomb can be placed on the _“PlayScreen”_. Wei worked on creating a sprite sheet for the bomb, which is a Voltorb. In addition, I also added a score function to the game for every block that is broken. Currently, the game is more like Pac-man than Bomber-man, but it can be easily switched since their concept is alike. 

```java
private String[] song = {"battle (vs wild pokemon).mp3", "ending.mp3", "lavender town's theme.mp3","pokemon center.mp3", "the road to lavender town - from vermillion.mp3", "the road to viridian city - from palette.mp3"};
i = random.nextInt(5);
private Random random = new Random();
Sound sound = Gdx.audio.newSound(Gdx.files.internal(song[i]));
```

Overall I wouldn’t call this game anywhere near complete, but we polished what we had thus far and fixed a lot of bugs. The more I advanced the project the more bugs there were, it felt like as if I was using Flex Tape to seal the project together. 
<br><img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/Finalproduct2.gif">

### Takeaways:
Work with what you **HAVE**, don’t keep trying to push *forward* when your previous step was *incomplete*. I should’ve worked more on actual polishing than adding since it introduced a LOT of bugs and took a long time to fix those bugs in addition to the already existing ones.


<b>[&larr; Back](Entry_8.md) | [First Entry](Entry_1.md) | [README](../README.md)</b>
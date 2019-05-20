### Week 7:

Week 7 was a messy week with everyone panicking to put all the scrapes together to make a MVP. Wei was making a MVP map and controls. I was initially going to help with the MVP, but soon afterward I found that **[Wei](https://github.com/weiz9762/java-independent-study/blob/master/entries/entry07.md)’s** files seem to be incompatible and had trouble running the file in IntelliJ. I tried to run the file on multiple cloud IDEs like **C9**, **Codenvy**, **REPL**, and **Codiva** but had no luck. **Codenvy** and **REPL** could run **swing**, and **Codenvy** could even run **JavaFX**, but unfortunately, none could run **LibGDX**, which was the core of what we needed (plus the server on Codenvy was really **REALLY** slow). So instead I decided to dedicate the week to find the music and sprites files for the game.

#### Sprites:

Finding the sprites was the first step, seeing that most of the sprites that we wanted were spread apart within different sprite sheets. I was able to find all necessary sprites from 8 different sprite sheets and gifs. ([I used a gif to sprite converter](https://ezgif.com/gif-to-sprite)). Then the real challenge started, I had to resize every sprite so that that “seemed” to be of equal size, then I resized them using [resizeimage.net](https://resizeimage.net/), and finally, I use photoshop to remove all the background from the sprite sheet. I thought that removing the background color would be easy since the background was all the same color - I was wrong. I spent over 3 hours removing the background and replacing the colors that were blended. After that I used the [LibGDX texturepacker](https://github.com/libgdx/libgdx/wiki/Texture-packer) to combine all the textures. Then it returned a .atlas file and the joint file.


The next step is the grab the graphics for each item, **WHEN** (and **IF**) we implant the item.

<img src = "">
<img src = "">
<img src = "">
<img src = "">
<img src = "">

#### Music:

Finding the music was simple enough, I found an [youtube video](https://www.youtube.com/watch?v=WnI7skE4_9k) which had the entire soundtrack and the time of each song underneath, so I downloaded the whole track and used **DaVinci Resolve** to cut out multiple sound clips. The harder part was finding the sound of the Eevee and Pikachu, but likely I found a [website](https://downloads.khinsider.com/game-soundtracks/album/pokemon-sfx-gen-3-ruby-sapphire-all-sound-effects-sfx) which contains the sound of each pokemon from pokemon red with a downloaded link with solved my problem.

Then I learned how to play each audio within JavaFX: 
```java
InputStream music;
//In case it fails
try{
	music = new FileInputStream(new File(“filepath”));
	AudioStream audio = new AudioStream(musicc);
	AudioPlayer.player.start(audio);
}case{
JOptionPane.showMessageDialog(null,”Error”);
}
```
```java
import javafx.scene.media.Media; 
import javafx.scene.media.MediaPlayer;
 import java.io.File;

String audioFile= "filepath.mp3";
Media sound = new Media(new File(musicFile).toURI().toString()); 
MediaPlayer mediaPlayer = new MediaPlayer(sound); 
mediaPlayer.play();

```
My current plan is to have a song for the home screen and one for the ending. While the rest will be randomized within the game.


#### Takeaways and goals:

Communication and collaboration are key. Since Wei and I are using different operating systems, when he sent his project my computer was unable to convert it. My first task for week 8 is to find a way to be able to covert his file into my IntelliJ so I can start helping with the backend and logic. Our first goal should have been to find a *cloud IDE*, but we never ended up finding one, which makes teamwork much harder than it's supposed to be.
<br>
The multiplayer will have to wait till after the MVP and a smooth project.
<br>

<b>[&larr; Back](Entry_6.md)  |
[Next &rarr;](Entry_8.md) | [README](../README.md)</b>
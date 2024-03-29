# lrc_SyncedLyrics_v2
Draft for format specs of lrc(SyncedLyric) v2. Please contribute

Will need a WYSIWYG editor if someone is using every feature.

file extension - .lrc, .music, or add it to metadata

purposes - lyrics, kareoke with time and pitch, Chords, meaning, translation

### Automation
All features for creating .lrc can be automated except Meaning.

Synced Lyrics can be retrived or Speech Recognition can time lyrics.

Chords can be automated (using software like Riffstation) or retrived from server.

Vocal Melody can be exracted automatedlly using free software like melody.ml to Isolate the vocal range and covert it to MIDI using https://www.sonicvisualiser.org/tony/ https://github.com/DamRsn/NeuralNote.

Translation retrived or can be automated using Google Translate.

## 0. Player to read filename with type speficied

If a audio file is played and there is a .lrc in the same directory or it is specefied in player
the .lrc can be named
```
sameasaudiofilename_translation.lrc
sameasaudiofilename_meaning.lrc
~sameasaudiofilename_chords.lrc (.chordpro)
```
1 file can have all 3 chords, meaning, translation

## 1 .lrc/SyncedLyrics version info

Format 

```
[lrc version:2]
```

## 2 Singer - A song may have multiple singers

Also See - Extended LRC - (Wikipedia repmved it) https://en.wikipedia.org/wiki/LRC_(file_format)#Simple_format_extended
Walaoke_extension:_gender - https://en.wikipedia.org/wiki/LRC_(file_format)#Walaoke_extension:_gender

### Format

```
[00:12.00] [Singer:Jhon]Line 1 lyrics[/Singer:Jhon]
[00:16.00] [Singer:Luis]Line 2 lyrics[/Singer:Luis]
[1:01.00] [Singer:William,Luis]Line 3 lyrics
```

## 3 Contextual Meaning - by word/line/paragraph

### Format

```
[00:00.00] [Meaning] I walk a lonely road [/Meaning: The singer is feeling lonely and isolated, and is on a path that no one else is traveling with him. He may feel like he doesn't fit in with others and is struggling to find his place in the world.]
[00:15.67] [Meaning] Don't know where it goes [/Meaning: The singer is uncertain of where the path will take him, and is unsure of what the future holds.]
[00:28.03] [Meaning] My shadow's the only one that walks beside me [/Meaning: The singer feels alone and abandoned, as represented by his shadow being the only companion on his journey.]
[00:42.25] [Meaning] I walk this empty street [/Meaning: The singer is walking down a street that feels barren and lifeless, emphasizing his feelings of loneliness and isolation.]
[00:53.04] [Meaning] On the boulevard of broken dreams [/Meaning: The "boulevard of broken dreams" is a metaphor for a place where people go to give up on their hopes and aspirations, and the singer feels like he is a part of this world of lost dreams and broken promises.]
```

## 4 Language Translation - Dictionary/Contexually per Word

When using translation specify lanuages eg. German to English  `de>en`
I file can have multiple translations

Dictionary in the player may not work as word has to be explained contexually and as used in gerneral/other cases.

### Format

```
[00:00.00] [WordMeanind,de>en]Überheblich[/WordMeanind:Arrogant], [WordMeanind]überlegen[/WordMeanind:consider]
```

## 5 Foreign Language Translation - Per Line/Phrase

### Format

```
[00:00.00] Tuuli tuule sinne [PhraseMeanind,fi>en]missä muruseni on[/PhraseMeanind:Literal:Where my loved ones are,CommonUsage:where's my baby?]
[00:00.00] Leiki hetki hänen hiuksillaan
[00:00.00] Kerro rakkauteni, kerro kuinka ikävöin
[00:00.00] Kerro, häntä ootan yhä vaan
```

## 6 Languages - Just metadata for song like "[ar:Lyrics artist]"

### Format

```
[language:Languages in the lyrics]
example [language:en,es,de]
```
## 7 UI for Translation and Meaning Feature

![ui](https://user-images.githubusercontent.com/105455604/168247326-d772633e-c073-4928-9400-ada37fa4817d.png)

When meaning mode from the top button is selected hovering over will show line, phrase or paragraph hilighted depening on context (when explaing song lyrics only one line or paragraph is sufficient) 

When translation mode is selected hovering over will hilight phrases (as small as possible) giving meaning of the phrase and words used trageted for langauge learning.

## 8 Milliseconds Word accuraccy for Karaeoke Mode

Also See - https://en.wikipedia.org/wiki/LRC_(file_format)#A2_extension:_word_time_tag
LRC Enhanced Format - https://en.wikipedia.org/wiki/LRC_(file_format)#A2_extension:_word_time_tag https://en.wikipedia.org/wiki/LRC_(file_format)#Enhanced_format

Words with milliseconds accuracy - Will hilight words as they are being played. This will be usefull for kareoke.

### Format (same as https://en.wikipedia.org/wiki/LRC_(file_format)#A2_extension:_word_time_tag)

```
[Verse 1]
[00:00.00]I <00:00.00> walk <00:00.38> a <00:00.52> lonely <00:00.95> road
[00:01.79]The <00:02.19> only <00:02.40> one <00:02.79>
[00:03.08]that <00:03.25> I <00:03.40> have <00:03.70> ever <00:03.90> known
[00:05.00]Don't <00:05.18> know <00:05.36> where <00:05.54> it <00:05.72> goes
[00:07.15]But <00:07.32> it's <00:07.60> home <00:07.91> to <00:08.08> me, <00:08.23> and <00:08.45> I <00:08.61> walk <00:08.81> alone

[Chorus]
[00:14.15]I <00:14.38> walk <00:14.57> this <00:14.72> empty <00:15.04> street
[00:18.17]On <00:18.38> the <00:18.51> Boulevard <00:18.89> of <00:19.05> Broken <00:19.35> Dreams
[00:20.69]Where <00:20.89> the <00:21.07> city <00:21.27> sleeps
[00:26.14]and <00:26.32> I'm <00:26.50> the <00:26.68> only <00:27.06> one, <00:27.24> and <00:27.45> I <00:27.61> walk <00:27.81> alone
```

## 9 Custom Color - for expression

Format

```
[02:16.00] [cr=#dc143c]Destroy yourself, see who gives a[/cr] [cr=#420612]duck[/cr]
[02:18.00] See who gives a duck
```
## 10 Custom Size - for expression

This can be turned off when using slidding lyrics depending of screen types. For example on phone with scrooling lyrics size can be hard to do.

### Format

```
[02:16.00] [sz=10]Destroy yourself, see who gives a[/sz] [sz=20]duck[/sz]
[02:18.00] See who gives a duck
```

## 11 Full Karaeoke - with MIDI for voice melody with pitch recognision and midi roll

A midi of voice melody can be supplied with audio files and the player can show midi roll and take mic input to work as a kareoke that can also work as a sining learing method.

![image](https://user-images.githubusercontent.com/105455604/168251330-d98a8d35-936d-44b7-9988-b86f71f4a67c.png)

It is "not similar" to https://en.wikipedia.org/wiki/CD%2BG  https://en.wikipedia.org/wiki/MP3%2BG

Vocal Melody can be exracted automatedlly. Isolate the vocal range and then that file can be used to generate to midi.

## 12 Chords

Use https://github.com/ChordPro/chordpro

Client may have ablity to transpose scale, have "no capo version", or show chord progression eg. `II V IV`


#### Old Proposed Format

```
[00:22.37] [cr]I walk a [/cr=Em][cr]lonely road, [/cr=G]the [cr]only one that [/cr=D][cr]I have ever known[/cr=Em]
[00:29.45] [cr]Don't know where it [/cr=G][cr]goes,[/cr=Em] [cr]but it's home to me [/cr=G][cr]and I walk alone[/cr=Em]
[00:36.72] [cr]I walk this empty[/cr=Em] [cr]street[/cr=G][cr]On the Boulevard of Broken Dreams[/cr=D]
[00:43.78] [cr]Where the city[/cr=Em] [cr]sleeps[/cr=G][cr]and I'm the only one and I walk alone[/cr=Em]
[00:57.58] [cr]I walk alone,[/cr=Em] [cr]I walk alone[/cr=G][cr]I walk alone[/cr=D][cr]I walk alone and I walk a...[/cr=Em]
```

## 13 Censoring Words

Add option to convert words like fuck, shit to F**k and S**t

https://github.com/LDNOOBW/List-of-Dirty-Naughty-Obscene-and-Otherwise-Bad-Words

## Also See

ID3 Specs https://id3.org/Lyrics3v2
foobar2000 lyrics component https://github.com/openlyrics/openlyrics
https://github.com/Aegisub/Aegisub

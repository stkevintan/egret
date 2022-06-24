---
{"dg-publish":true,"permalink":"/midi/midi-file/","tags":"gardenEntry","dgHomeLink":true,"dgPassFrontmatter":false}
---


Here are answers to questions about MIDI files. Questions are:

[What's a MIDI file?](http://midi.teragonaudio.com/tutr/midiform.htm#q1)  
[How is a MIDI file different than a WAVE or MP3 file?](http://midi.teragonaudio.com/tutr/midiform.htm#q2)  
[Why does a particular MIDI file play incorrectly?](http://midi.teragonaudio.com/tutr/midiform.htm#q3)  
[What's an RMID file?](http://midi.teragonaudio.com/tutr/midiform.htm#q4)  
[How do I play a Macintosh MIDI file on an IBM PC?](http://midi.teragonaudio.com/tutr/midiform.htm#q5)  
[How do I transfer a hardware sequencer's patterns to my computer for use with my sequencer software?](http://midi.teragonaudio.com/tutr/midiform.htm#q6)  
[How do I create an audio CD from a MIDI file (or convert a MIDI file to a WAVE file)?](http://midi.teragonaudio.com/tutr/midiform.htm#q7)

# What's a MIDI file?

A MIDI file is a data file. It stores information, just like a text (ie, ASCII) file may store the text of a story or newspaper article, but a MIDI file contains musical information. Specifically, a MIDI file stores MIDI data -- the data (ie, commands) that musical instruments transmit between each other to control such things as playing notes and adjusting an instrument's sound in various ways.

MIDI is binary data, and a MIDI file is therefore a binary file. You can't load a MIDI file into a text editor such as Notepad and view it. (Well, you can, but it will look like gibberish, since the data is not ASCII, ie, text. Of course, you can use my [MIDI File Disassembler/Assembler utility](http://midi.teragonaudio.com/progs/software.htm#dsm) to convert a MIDI file to readable text, edit it in Notepad, and then convert it back to a MIDI file using the same software).

The MIDI file format was devised<sup>设计</sup> to be able to store any kind of MIDI message, including System Exclusive messages, along with a timestamp for each MIDI message. A timestamp is simply the time when the message was generated. Using the timestamps, a sequencer can playback all of the MIDI messages within the MIDI file at the same relative times as when the messages were originally generated. In other words, a sequencer can playback all of the note messages, and other MIDI messages, with the original "musical rhythms". A MIDI file can also store other information relating to a musical performance, such as tempo, key signature, and time signature. A MIDI file is therefore a generic, standardized file format designed to store a "musical performance", and is used by many sequencers. A MIDI file even has provisions for storing the names of tracks in a sequencer, and other sequencer settings.

MIDI files are not specific to any particular computer platform or product.

There are 3 different "Types" (sometimes called "Formats") of MIDI files. A Type 0 file contains only one track, and all of the MIDI messages (ie, the entire performance) are placed in that one track, even if this represents many musical parts upon different MIDI channels. A Type 1 file separates each musical part upon its own track. Both Type 0 and 1 store one "song", "pattern", or musical performance. A Type 2 file, which is extremely rare, is akin to a collection of Type 0 files all crammed into one MIDI file. Type 2 is used to store a collection of songs or patterns, for example, numerous drum beats. (If you need to convert a MIDI file to the various Types, use my [Midi File Conversion utility](http://midi.teragonaudio.com/progs/software.htm#convert)).

Besides sequencers, other software and hardware devices may use MIDI files. For example, a patch editor may store an instrument's patch settings in a MIDI file, by storing System Exclusive messages (received from the instrument) within the MIDI file. In this case, the patch editor may not care about the timestamp associated with each SysEx message.

# How is a MIDI file different than a WAVE or MP3 file?

A MIDI file stores MIDI messages, which are commands that tell a musical device what to do in order to make music. For example, there is a MIDI message that tells a device to play a particular note. There is another MIDI message that tells a device to change its current "sound" to a particular patch or instrument. Etc. The MIDI file also stores timestamps, and other information that a sequencer needs to play some "musical performance" by transmitting all of the MIDI messages in the file to all MIDI devices. In other words, a MIDI file contains hundreds (to thousands) of instructions that tell one or more sound modules (either external ones connected to your sequencer's MIDI Out, or sound modules built into your computer's sound card) how to reproduce every single, individual note and nuance<sup>细微差别</sup> of a musical performance.

A WAVE file stores a digital audio waveform. This data must be played back upon a device with a Digital To Analog Converter (ie, DAC) such as a MIDI sampler (ie, the AKAI S1000 for example) or a computer sound card's DAC. There are no timestamps, or other information concerning musical rhythms or tempo stored in a WAVE file. There is only digital audio data. Typically, a WAVE file is used to store a looped, single-pitched waveform (which a sampler transposes and plays back over a range of MIDI note numbers), or a short, non-looped percussive sound or sound effect, or often a digital audio recording (ie, stereo mixdown) of some musical performance stored upon your hard drive.

The only way to record and store a musical performance within a WAVE file is to digitize the audio output of all instruments while they play that performance. The result will be a typically large WAVE file that represents the digitized "sound" of all instruments playing the musical piece in realtime. The act of doing such is often referred to as "Hard disk recording" because the WAVE data usually has to be recorded directly to a large Hard Drive while the DAC digitizes the performance.

A MIDI file allows easy editing of the individual musical parts, because each part is usually assigned to its own MIDI channel, and it's easy to separate that part's MIDI data from the other parts' MIDI data, based upon the MIDI channel in each MIDI message. On the other hand, you can't easily separate the digital audio data of one instrument from the digital audio data of another instrument, if the two were digitized simultaneously into one WAVE file. For editing of individual musical parts, each part should be digitized and stored in its own WAVE file. Due to the difficulties in separating musical parts from a WAVE file, a conversion from WAVE format to MIDI format is not too feasible, although the reverse is not a problem.

One benefit of a WAVE file is that its "sound" is not usually dependent upon the playback device. A WAVE file should sound the same upon different equipment (with reasonably similiar specs). On the other hand, a MIDI file can sound considerably different upon different MIDI gear. This is because the MIDI file doesn't dictate what means an instrument uses to produce its sound. The MIDI file may sound very different upon an instrument that uses FM synthesis than it will sound upon an instrument using "wavetable synthesis" (ie, looped, digital audio waveforms in ROM). But, standards such as _General MIDI_ seek to alleviate some of the discrepancies between MIDI devices.

An MP3 file, like a WAVE file, stores digital audio data. So a MIDI file and an MP3 file are different in exactly the same way that a MIDI file and a WAVE file are different. Indeed, a WAVE and MP3 file are two different ways of storing the exact same type of data. The primary difference between a WAVE and MP3 file is that the latter uses compression to squeeze the data down in size, resulting in a typically much smaller file size.

# Why does a particular MIDI file sound so bizarre when played back upon my equipment? It sounds like "jungle bunnies from Hell" are performing. And every time that I play the file, it sounds different depending upon what other MIDI file I played previously. Sometimes, certain parts don't sound at all, and other times they do.

A MIDI file may sound odd upon your equipment for one of two reasons.

First, the MIDI file may not have the proper "MIDI setup events" at the beginning of the file. If these events are missing, then the MIDI file won't properly setup your equipment with the necessary instrumentation, and panning and volume (ie, mix), etc, that is necessary to play the MIDI arrangement as it was intended by the creator (henceforth referred to as the author) of the MIDI file.

By "MIDI setup events", I'm referring to certain MIDI messages. For one thing, the MIDI file may not contain MIDI Program Change messages at the start of the arrangement to setup each MIDI sound module to play the desired Patches. The net result is that what was supposed to be a Piano part, for example, may end up being played upon a module that is currently setup with a Tuba patch. Having a Tuba play the Piano part probably isn't going to sound good.

Furthermore, the author may have neglected to put some important controller events at the start of each track. There are controller events to set volume, panning, reverb and chorus levels, modulation (ie, vibrato amount), etc. For example, if volume controllers are omitted, then the file will playback with whatever volumes all of your sound modules are currently set to. If a previously played MIDI file has "faded out" the volume of a particular module, then that module may not even be sounding the part that it is supposed to be playing. Other clues that these important events may be missing is if parts inexplicably play with vibrato, odd panning, out of tune, or with the sustain pedal held.

Very often, an author forgets to place these important "setup events" at the start of the arrangement. There are two ways to fix such a MIDI file. You can manually edit it, inserting the proper setup events for your equipment. I'll describe this process below. Or, you can do it the easy way by using my MIDI File Cleanup utility, available upon this web site.

If your sound modules understand the MIDI _Reset All Controllers_ message, I recommend inserting this at the very start of each track. This will instruct your module to set all of the MIDI controllers it understands (and usually Pitch Wheel and Aftertouch) to default values.

**NOTE:** You only need to put these setup events upon tracks that are assigned to different MIDI channels. For example, if both track 1 and 2 are assigned to the same MIDI channel, then you need to put the setup events in only one of those two tracks.

Also, insert a Bank Select controller with a value of zero, and then insert an appropriate Program Change event for each track. For example, if the name of the track is "Harpsichord", and you're using a General MIDI module, insert a Program Change for program #7 (or 6 if your software counts the first program as 0 instead of 1). (See the General MIDI article for a listing of GM programs). Make sure that the Program Change event occurs after the Bank Select. For the Drum tracks, I recommend a Bank Select controller of 0, and a Program Change of 0. Again, you only need the setup events on one drum track if all drum tracks are assigned to the same MIDI channel.

If your sound module doesn't recognize _Reset All Controllers_, then I recommend putting in the following controllers with these values: Volume (controller #7) at a value of 100, Pan (10) at 64, Expression (11) at 127, Mod Wheel (1) at 0, Hold Pedal (64) at 0, Effects Level (91) at 64 (assuming that it controls Reverb, otherwise set it at 0), and Chorus Level (93) at 0. For modules that recognize any of the following controllers, you may wish to also add that respective controller: Balance (8) at 64, Soft Pedal (67) at 0, Portamento (65) at 0, and Legato Pedal (68) at 0. To reset Pitch Wheel Range to +/- 2 steps, insert the following 3 controllers in this order: NRPN MSB (98) at 0, NRPN LSB (99) at 0, and Data Entry Slider (6) at 2. Finally, you should also reset the Pitch Wheel to 0, and Channel Pressure to 0 (as well as Key Pressure if your module implements that).

Alternately, some sequencers have a feature to automatically spit out default setup events for each track before playing any MIDI file. This may cure some mix problems, but you'll probably still need to adjust instrumentation (ie, insert Program Change).

On the other hand, the author may have included setup events at the start of the MIDI file, but your MIDI equipment's Patch set and MIDI channel assignments may be different than the ones used by the author. One very annoying ramification of this is when different MIDI channels are used for drum parts. The net result is that you often end up hearing instrumental parts (ie, piano, guitar, etc) played on drum sounds, and drum notes being played as piano/guitar/etc notes. Also, if parts are being played in odd octaves (ie, the part sounds like it's a few octaves too high or low), this is another ramification of conflicts between the equipment which the author used and your own equipment.

The [General MIDI specification](http://midi.teragonaudio.com/tutr/gm.htm) is designed to get everyone to setup and use their equipment in a compatible way. For example, all drum parts are always upon MIDI channel 10, and all drum sound modules should be set to this channel. The GM spec details a lot of ways in which gear should be setup, in order to eliminate as many trivial incompatibilities as possible. If the author uses GM-compliant sound modules to create the MIDI file and remembers to put the proper MIDI setup events in the MIDI file, and you play that file with some GM-compliant sound modules, you'll hear the proper instrumentation and mix.

**NOTE:** If a MIDI file seems to turn off the Drum Kit permanently in a Roland card (ie, it seems to disable the Drum Kit for all MIDI files that you play afterwards), then the problem is likely due to a Bank Select controller and/or Program Change in one of the drum tracks. If a Roland card is asked to switch its Drum Kit to a bank/program that doesn't exist in the card, sometimes the Roland card will disable the drum kit. Simply edit the file to change that Bank Select controller and/or Program Change event to a value understood by the Roland card, for example, set the value to bank 0 and program 1.

# What's an RMID file (ie, it has a filename extension of .rmi)? How do I extract the MIDI data from it? My sequencer won't read it.

An RMID file is simply a MIDI file that has some extra bytes prepended to it. If you remove those extra bytes, then you'll end up with a standard MIDI file. To edit the RMID file, you need to use a program that edits binary (ie, not text) files to chop off those extra bytes (ie, characters) at the start of the file. Such a program is usually referred to as a "hex (or binary) editor. Do not use a text editor such as Notepad.

Load the RIFF file into the hex editor, and chop of all bytes before you see the 4 ascii characters of "M', 'T', 'h', and 'd' in that order. (ie, The hex editor should have a split-window display were it shows the value of each byte, and then displays its ascii character on the other side of the window. Look at the ascii character display). Do not chop off the 'M', 'T', 'h', 'd' (as that is the start of the embedded MIDI file) -- just all characters before those four.

A free alternative is to use my [MIDI File Disassembler/Assembler utility](http://midi.teragonaudio.com/progs/software.htm#dsm) to convert the MIDI file to readable text. This will automatically strip out the RMID header. Then, you can immediately use the same utility to convert the text file back to a MIDI file.

# How can I play, on my IBM PC, a MIDI file that was made on a Macintosh? My sequencer won't read it.

A MIDI file made on a Macintosh may likely have 128 extra bytes prepended to it (ie, a Mac Binary Header). If you remove those first 128 bytes (ie, all the bytes before you see the first 4 characters of 'M', 'T', 'h', and 'd') then you'll end up with a standard MIDI file. Use a program that edits binary (ie, not text) files to chop off the first 128 bytes (ie, characters).

A free alternative is to use my [MIDI File Disassembler/Assembler utility](http://midi.teragonaudio.com/progs/software.htm#dsm) to convert the MIDI file to readable text. This should automatically strip out the Mac header. Then, you can immediately use the same utility to convert the text file back to a MIDI file.

# Is there some way to take patterns stored in a proprietary format on some disk for my hardware sequencer (or stored in its internal memory) and transfer them to my computer so that I can edit those sequences with some computer sequencer software such as CakeWalk? My computer can't seem to read the disks that my hardware sequencer uses, and some proprietary data dump to the computer is no help in getting CakeWalk to recognize the data as musical sequences.

If your hardware sequencer outputs MIDI Start/Stop and MIDI clock messages (or can sync to those), then it's very easy. You'll need some sequencer software on your computer capable of syncing to MIDI Clock (or which generates MIDI Start/Stop and Clock messages if your hardware sequencer can alternately sync to MIDI). For example, CakeWalk is such a program (and I'll refer to it below).

Assuming that your hardware sequencer outputs MIDI Start/Stop and MIDI Clock -- first, connect the MIDI Out of the hardware sequencer into the computer's MIDI In. Next, set CakeWalk's sync to MIDI instead of Internal (ie, set the computer sequencer software to sync to incoming MIDI Clocks). Then, set CakeWalk's Settings->Channel Table so that each MIDI channel is being recorded upon a separate track (ie, set MIDI channel 1 to track 1, MIDI Channel 2 to track 2, etc). Make sure that you disable any quantize of data being recorded, or set the quantize to a very small note value. Then, you need to get CakeWalk ready to record.

Now simply press the Play button on the hardware sequencer, and let it play all of its MIDI tracks into CakeWalk. (ie, CakeWalk should kick into record when you press the hardware sequencer's Play button if the sync is working). For all CakeWalk knows, it's merely recording the MIDI output of a bunch of daisy-chained synths being played by numerous musicians live. CakeWalk doesn't need to know that it's recording the output of another sequencer. In other words, you're transferring the data by playing it back, and simultaneously recording it, in real-time.

Of course, this doesn't transfer such things as track names, key and time signatures, tempo settings, and other display settings that your hardware sequencer may support. It also separates the MIDI data by channel assignment which may be different than the way that the tracks were arranged upon your hardware sequencer. (For example, if your hardware sequencer had 3 separate tracks all containing data upon MIDI channel 1, these 3 will be merged into 1 CakeWalk track). But it captures all of the MIDI data with the proper timing, and that's the important thing.

To speed up the transfer process, you could increase the tempo on your hardware sequencer. But you don't want to increase the tempo too much as this transfer method inevitably introduces slight deviations in the timing of individual events, and that is made worse by faster tempos. (Hopefully, your ear won't hear those deviations, but if any timing sounds too odd, then slow down the tempo when you transfer the file).

If your hardware sequencer supports syncing to MIDI Clock, you can transfer a MIDI file back by reversing the above setup (ie, setting CakeWalk to output MIDI Start/Stop and Clocks, and set the hardware sequencer to sync to MIDI. Connect the computer's MIDI Out to the hardware sequencer's MIDI In, press record on the hardware sequencer, and then play the MIDI file in CakeWalk).

This transfer method isn't quite as precise nor convenient than if you use a hardware sequencer that writes standard MIDI files upon floppy disks that can be read by your computer (or have a computer program that can accept a dump from your hardware sequencer and convert it to standard MIDI format). But it works between any 2 sequencers.

# How do I create an audio CD from a MIDI file (or convert a MIDI file to a WAVE file)?

An audio CD (designed to be played in standalone CD players) contains tracks of digital audio (in WAVE file format). There is also some "control information" on the CD that tells the CD player how many musical tracks are on the CD, and in what order to play them. So, to create an audio CD, you need software that is specifically written to do that, such as Adaptec's "Easy CD Creator" (which allows you to create various types of CD's, among them, audio CD's) or Nero Express (or Burning ROM).

Easy CD Creator, or Nero Express, are typical of programs that allow you to create an audio CD. The software lets you pick out various WAVE files (or sometimes MP3, or other digital audio formats -- but not MIDI files) and drop them into a "layout". The layout simply determines in what order the WAVE files will become musical tracks on the CD. Then, you tell the software to burn an audio CD using those WAVE files.

So, the major task is first converting your MIDI file to a WAVE file so that you can subsequently use Easy CD Creator to create an audio CD. To do this, you need a program capable of recording a WAVE file, such as "Cool Edit" or "Sound Forge". And you need a MIDI player program such as Cakewalk or Cubase or even something as simple as the Windows Media Player. (If you're using a program that can play MIDI tracks while it is also recording a digital audio track, such as Cakewalk Pro Audio, then you can do everything with just the one program).

To convert a MIDI file to a WAVE file, follow these steps:

1.  Attach the audio out of your MIDI sound module(s) to the line in jack of your sound card. If your sound module is built into the sound card, simply run the sound card's "line out" (or "speaker out") back into its own "line in" (or "microphone").
    
2.  Open the MIDI file in the MIDI player program (ie, Windows Media Player).
    
3.  Run the digital audio recording program. Set it to record a stereo, 16-bit, 44Khz audio track. Also, select your sound card's input as the recording source.
    
4.  Put the digital audio recording program into record. (Before doing this, you may want to first set the recording level by playing the MIDI file while you adjust the recording program's record volume).
    
5.  Quickly flip back to the MIDI player program and put it into play. Now let the MIDI file play back while the digital audio recording program is recording the sound of your sound module playing that MIDI file.
    
6.  When the playback ends, stop the digital audio recording. Trim off any excess silence at the start and end of the audio track, and then save it in WAVE file format. Now you're ready to add this WAVE file to your CD software's "layout".

In lieu of using the above procedure to create a WAVE mix from a MIDI file, there are also some programs that can directly convert a MIDI file to a WAVE file. Such a program uses its own internal set of waveforms to mathematically create the WAVE mixdown (rather than using the sound of your own sound modules). So, if you don't like the program's built-in sounds, then you'll either have to find a new waveform set (if the program supports that -- some programs support loading SoundFonts), or try another such program.

### Recommended reading:

[What is MIDI?](http://midi.teragonaudio.com/tutr/whatmidi.htm)  
[What is a sequencer?](http://midi.teragonaudio.com/tutr/whatsseq.htm)  
[General MIDI](http://midi.teragonaudio.com/tutr/gm.htm)
# Paraphonic Moog Voyager

This is a Max patch to add paraphonic performance capability to a Moog Voyager.

## Algorithm

The algorithm and implementation are both a bit finnicky and will not
fit every playing style.

The current algorithm may be best summarized as "three note legato".  A
first note on for the "root note" is received and retransmitted to the
Voyager.  Subsequent notes fill slots 2 and 3 and program the Osc2 and
Osc3 frequency and octave and mix as they are received.  But no note
on is sent for these subsequent voices.  A note off for the root note
is transmitted when either all notes are released or the root note
pitch changes.  A change of the root note pitch reprograms the Osc2
and Osc3 parameters accordingly.

Playability is very sensitive to the order in which notes are
received.  This affects the range of notes that can be expressed as
well.  For example, if Osc1 is set to the lowest octave then no note
more than a fifth below the root note can be played (a similar
situation exists in reverse when using the highest octave).

## Setup

Steps to set up are documented in the patch itself.  They are:

1. Connect the Voyager via both MIDI in and out, disable local control
   on the Voyager, and select the appropriate MIDI device in the
   patch.

2. Press the initial setup button to reset the Osc1-3 mix parameters.

3. Toggle the Osc1 octave knob on the Voyager to the desired setting.
   This allows the patch to track which octave the root note is
   playing in.

4. Fine tune the Osc3/Osc3 frequency offset using fifths.





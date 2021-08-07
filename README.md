## ioRouting.js
A script for MIDI/AUDIO routing in Max for Live devices.

### Usage
Check sample devices for further details.

#### Arguments of js object
> js ioRoutings.js *io-type* [*channel-offset*]
- io-type<br>
midi_inputs, midi_outputs, audio_inputs, or audio_outputs
- channel-offset (optional)<br>
number of channel pairs (zero-based counting)

#### Messages
- init<br>
    Calls initialize method. Must be called by bang from live.thisdevice, not loadbang or loadmess.
- setchannel<br>
    Arguments: channel-number [int]<br>
    Changes the routing channel by number of lists. (zero-based counting)
- settype<br>
    Arguments: type-number [int]<br>
    Changes the routing type by number of lists. (zero-based counting)

#### Output
- Out left outlet: Messages for live.menu objects; selector for the routing type (track or external device).
- Out right outlet: Messages for live.menu objects; selector for the routing channel (channel or subcategories).

Each live.menu objects connected to js has to be set attributes below;<br>
- Parameter Visibility -> hidden
- Initial Enable -> false

#### Miscellaneous
- This script use unofficial attributes for live.menu. The author does not own any responsibilities for using the script.
- Undoing a series of changes for MIDI input type or channel may cause extra revert for pulldown lists. (issue [#1](https://github.com/h1data/M4L-ioRouting-js/issues/1))

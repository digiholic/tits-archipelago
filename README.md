A Text Client that interfaces with [T.I.T.S](<https://remasuri3.itch.io/tits>) to throw items when certain triggers in a multiworld occur.

# What is T.I.T.S.?
T.I.T.S. stands for "Twitch Integrated Throwing System". It's a stream tool which allows viewers to toss things at streamers. It's mostly used by VTubers since the verisimilitude of cartoon objects thrown at a cartoon person is consistent and the tool has built-in integration with most VTube apps for things like physics reactions, but it can be used by anyone. You'd use the program and import custom models or sprites and set up trigger responses, which you could trigger with channel point redeems or bot commands or follow alerts or all sorts of other built-in triggers. However, it also has a Websocket API for custom integrations. That's where this client comes in. This is an extension of the basic Text Client that also connects to a running instance of T.I.T.S. on the local machine and sends trigger events to the program when certain things happen in your Multiworld. For a full list of which Triggers get fired, see the next post.

# Usage:
1. Run T.I.T.S. and enable the API through Settings menu. You may specify a port, or leave it at the default value of 42069
2. Define any number of Triggers with the specified names below, and adjust any settings you want. The entire "Trigger On" section in the center is not relevant for API triggers and can be ignored.
3. Install the attached APWorld
4. Run the `T.I.T.S. Integrated Text Service` from the Archipelago Launcher
5. Connect to a running Multiworld game. If T.I.T.S. had its port number left at default, it will auto-connect. Otherwise, you can use the `/tits-connect [optional_port]` command to connect on a different port.

# Trigger Endpoints
These are the Trigger names that will be called by the Client, and when. You can also find this list in the client itself with the command `/tits_help`

- **AP-Receive** - When receiving any item
- **AP-Receive-Progression**- When receiving a progression item
- **AP-Receive-Useful**- When receiving a useful item
- **AP-Receive-Filler**- When receiving a filler item
- **AP-Receive-Trap**- When receiving a trap item
- **AP-Send** - When sending any item
- **AP-Send-Progression**- When sending a progression item
- **AP-Send-Useful**- When sending a useful item
- **AP-Send-Filler**- When sending a filler item
- **AP-Send-Trap**- When sending a trap item
- **AP-Goal**- When you have achieved your goal
- **AP-Deathlink**- When a Deathlink is received, regardless of source (including yourself!)

The `AP-Receive` and `AP-Send` triggers are a bit special, if one is set, none of the other `-Receive` or `-Send` triggers will run. The idea is to use it when you just want _something_ thrown, and to use the specialized ones if you want something different to happen based on progression. Any triggers that are not set up in T.I.T.S. will be quietly skipped. As such, all are optional.
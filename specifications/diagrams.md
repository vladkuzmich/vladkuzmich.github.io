## Conceptual diagrams for the BARB database

This is the high level conceptual diagram that is used to structure the API.

Please note:

- This is a work in progress
- This is not intended to be the data model for storage of the data (although it should get close to it).
- Some of the names of entities are selected to ensure continuity with the existing BARB set up. For example the `Programme` entity should really be called something like `ProgrammeTransmissionInstance` as each separate transmission of a programme counts as a separate programme.
- A `ViewingSession` is the coming together of a `PanelMember` or `Guest`, a `Device` and a `Station`.

```mermaid
 classDiagram
   direction LR

   class Spot
   class Panel
   class Station
   class Programme
   class Platform
   class Sponsor
   class ProgrammeContent
   class Episode
   class Series
   class Product
   class Audience
   class SalesHouse
   class PanelMember
   class Guest
   class Household
   class Device
   class TV


	 TV --|> Device : is a
	 Device --|> Household : belongs to
	 PanelMember --|> Panel : is a member of a
	 PanelMember --|> Audience : is a member of an
	 PanelMember --|> Household : is a member of
	 PanelMember --|> ViewingSession : takes part in
	 Guest --|> ViewingSession : takes part in
	 Guest --|> Audience : is a member of an
	 Device --|> ViewingSession : is used in
	 ProgrammeContent --|> Programme: is included in
	 Episode --|> ProgrammeContent : is part of
	 Episode --|> Series : is part of a
	 Product --|> ProgrammeContent : can appear in
	 Sponsor --|> Programme: sponsors
	 Station --|> Spot: broadcasts
	 Station --|> Programme: broadcasts
	 Station --|> ViewingSession : is viewed in a
	 Programme --|> Platform: is transmitted on a
	 SalesHouse --|> Spot : sells a
 ```

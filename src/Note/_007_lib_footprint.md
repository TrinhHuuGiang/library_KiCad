## Topic

### Create new footprint
- In project manager choose function `Footprint Editor`
- `File -> New library -> Global/Project` then create first library `.kicad_mod`
- In the `Library tree` from left `tools bar`, Filter just created library
    - Right click on it then choose `New footprint`
- At the top tools bar click on label `Footprint properties`:
    - References: Default is Front Sinkscreen `F.Sinkscreen`. It keep default `REF**`, then auto exchange by `Reference` of `Symbol` will bind this `footprint`.
    - Value: Value can hide, by default it is `Fabrication - F.Fab` not be `Sink-screen`
    - Datasheet
    - Description: There are 2 fields `Description`, 1 for display on footprint, 1 for descript in library
    - Footprint name: name display in library
    - Component type: is optional, 3 option `through hole` `SMD` `unspecified`
- We can change view from `mm` to `mil` or opposite by the left toolbar
- At the top tool bar, we still see a option setup `pad/through hole` named `Default pad properties`


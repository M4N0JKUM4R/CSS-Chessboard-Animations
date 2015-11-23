# CSS-Chessboard-Animations

*This is just a fun experiment with CSS3 to check its usage and limitations. Alternatively, It can be easily achieved using JS to avoid the sequencing trouble and animation delay calculation. You can also use Animation libraries like GSAP's [Timelinemax](https://greensock.com/timelinemax)*


----------


#### Demos that could be achieved so far:

###### Short games:

[**Paul Keres Vs Edward Arlamowski**](http://manojkr.com/demos/chess-animations/paulvsedward.html)

###### Shortest Checkmates:

[**Scholar's mate**](http://manojkr.com/demos/chess-animations/scholars-mate.html)

###### Chess Basics:

*Piece movements:*

[**King**](http://manojkr.com/demos/chess-animations/king-movements.html)<br>
[**Queen**](http://manojkr.com/demos/chess-animations/queen-movements.html)<br>
[**Rook**](http://manojkr.com/demos/chess-animations/rook-movements.html)<br>
[**Bishop**](http://manojkr.com/demos/chess-animations/bishop-movements.html)<br>
[**Knight**](http://manojkr.com/demos/chess-animations/knight-movements.html)<br>
[**Pawn**](http://manojkr.com/demos/chess-animations/pawn-movements.html)

*Others:*

[**Castling**](http://manojkr.com/demos/chess-animations/castling.html)<br>
[**En passant**](http://manojkr.com/demos/chess-animations/en-passant.html)<br>
**Pawn-Promotion** - Included in [**Pawn movements**](http://manojkr.com/demos/chess-animations/pawn-movements.html)

*Openings*

**Giuoco Piano**- Included in [castling](http://manojkr.com/demos/chess-animations/castling.html)<br>
**French Opening (Steinitz variation)** - Included in [en-passant](http://manojkr.com/demos/chess-animations/en-passant.html)
**Caro-kann defence** - Included in [Paul Vs. Edward](http://manojkr.com/demos/chess-animations/paulvsedward.html)


----------


#### Movement classes: 

###### King, Queen, Rook, Pawn movement

- **Move upwards:** `move-up-*`

- **Move downwards**: `move-down-*`

- **Move left:** `move-left-*`

- **Move right:** `move-right-*` 

*spans from 1 to 7.


###### Bishop, Queen movement

- **Move left, diagonally up:** `move-left-up-*`

- **Move right, diagonally up:** `move-right-up-*`

- **Move left, diagonally down:** `move-left-down-*`

- **Move right, diagonally down:** `move-right-down-*` 

*spans from 1 to 7.

###### Knight movement

- **Move left:** `move-up-left-short`, `move-up-left-long`, `move-down-left-short`, `move-down-left-long`

- **Move right:** `move-up-right-short`, `move-up-right-long`, `move-down-right-short`, `move-down-right-long`


----------


#### Event classes: 

##### Castling:

- *King side castle:*

`move-right-2` and `move-left-2` on King(`.e1 > img`) and Rook(`.h1 > img`)  respectively.

- *Queen side castle:*

`move-left-2` and `move-right-3` on King(`.e8 > img`) and Rook(`.a8 > img`) respectively.

##### Piece classes:

- **Captured Piece:** Movement class & `remove-piece`
- **Promoted pawn:** `move-up-1` + `hidden-piece` and `promoted-piece`
- **En passant:** `move-left-up-1` and `remove-piece` 


----------


### Special events:

##### Highlighting and attacked piece:

`highlight-square` class on all the squares being targeted before the attacked piece. For eg: If a piece on a3 attacks a piece on a7, highlight on a3, a4, a5, a6 and a7 uses the `attacked` class.


##### Checkmate:

`winner` class on the winning king square.

`defeated` class on the losing king square.



----------
 

### Info:

- Chessboard squares are created using [viewport](https://css-tricks.com/viewport-sized-typography/) units.

- Chess icon set by [Wikimedia commons SVG Chess pieces](https://commons.wikimedia.org/wiki/Category:SVG_chess_pieces)

- Movement classes could be done using `left` and `right` along with `position: relative` or maybe `margin` properties as well, but `transform: translate*()` properties work well because of GPU performance as stated by an article here by Paul Irish: [Why Moving Elements With Translate() Is Better Than Pos:abs Top/left](http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/). You can also check the properties that trigger a reflow here: [CSS triggers](http://csstriggers.com)


----------


### Drawbacks:

The viewport units are not yet supported completely in [IE, Edge and some mobile browsers](http://caniuse.com/#feat=viewport-units).

There is currently no way to sequence CSS animations so that the second animation continues with the properties set after completion of the first animation.

[Reference](http://www.w3.org/TR/css3-animations/#animation-name-property)

> The `animation-name` property defines a list of animations that apply.
> If multiple animations are
> attempting to modify the same property, then the animation closest to
> the end of the list of names wins.

This is also demonstrated in the question here: [Extend the final state of the first animation for translated element](http://stackoverflow.com/questions/32224802/extend-the-final-state-of-the-first-animation-for-translated-element)

Found a way to overcome this drawback, have some suggestions to improve this or submit your own demos? Send me a pull request please. 




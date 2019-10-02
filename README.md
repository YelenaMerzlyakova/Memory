# Memory game

[Test your memory, are you any good?](https://yelenamerzlyakova.github.io/Memory/)

## Mission objectives
- Change things in the DOM (Aka canvas = cheating)
- react to keypresses
- collision detection

## The Mission
We want to recreate the game `memory`. It is a game where  you have a bunch of cards. Each card contains an image. Of each image there are exactly two cards. The cards are placed in a random order. You get to turn them around. If you turned around two cards they either turn back so you can't see their image if they did not match. And if they did match they stay image face visible.

### Must-have features
- Clicking cards turns them around
- Randomly position the cards
- Readme, but that shouldn't even have to be said
- Explanation on the page itself


### Features that I can still add
- Make it playable by keyboard
- Let a user define custom image urls
- Make it pleasing to look at
- Multiplayer (local)

## Result 

![mzmoey](https://github.com/YelenaMerzlyakova/Memory/blob/master/memory.png)

## Code

Here I am checking whether the cards match. If they match they are disabled and if not they flip back.

``` Javascript
function checkForMatch() {
    let isMatch = firstCard.dataset.framework ===
    secondCard.dataset.framework; 

    isMatch ? disableCards() : unflipCards();
}


function disableCards() {
    firstCard.removeEventListener('click', flipCard);
    secondCard.removeEventListener('click', flipCard);

    resetBoard();
}

function unflipCards() {
    lockBoard = true;
    setTimeout(() => {
        firstCard.classList.remove('flip');
        secondCard.classList.remove('flip');

        resetBoard();
    }, 1500);
}

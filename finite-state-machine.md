# Basic JavaScript Finite State Machine
#fsm #state #machine #javascript #game

## explanation
State machines make handling complex combinations of variables more convenient. Instead of handling every possible combination of states and actions you can only handle the particular combinations that make sense in your use case.

[This document](http://people.cs.vt.edu/~kafura/ComputationalThinking/Class-Notes/FSM.pdf) explains the concept of a state machine in much more detail (and much more clearly) than this brief article will.

I'm working on a game development project called [Unstable](http://unstablegame.com). This is a legacy project so I'm constantly looking for little improvements I can make without drastically reworking my build system and tooling. Implementing a state machine for some more complex objects is one of those such improvements.

This finite state machine was created for a Timer object in my game. It needed an initial paused state that could only be triggered to play once when the player first started moving. From there the pause and play states functioned as one would normally expect in a timer.

## FSM Source Code
```javascript
function fsm(states, initialState) {
    this.currentState = initialState;

    return {
        action: function(action) {
            if (states[this.currentState][action]) {
                states[this.currentState][action]();
            }
        },

        transition: function(state) {
            this.currentState = state;
        },

        currentState: this.currentState
    }
}
```
## State Constructor Object Format
```javascript
{
    state1: {
        action1: callback1
        action2: callback2
    },
    state2: {
        action1: callback1
    }
}
```

## FSM Implementation Example
```javascript
this.state = fsm(
    {
        playerUnmoved: {
            playerMoved: function() {
                this.state.transition('playing');
            }.bind(this)
        },
        paused: {
            play: function() {
                this.state.transition('playing');
            }.bind(this)
        },
        playing: {
            pause: function() {
                this.state.transition('paused');
            }.bind(this)
        }
    },
    'playerUnmoved'
);

this.state.action('pause');

this.state.action('play');

if (this.state.currrentState === 'playing') {
    // increment the timer's counter
}
```

## sources
http://people.cs.vt.edu/~kafura/ComputationalThinking/Class-Notes/FSM.pdf


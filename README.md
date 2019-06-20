# peek-for-tmux
The most useful smallest tmux trick by yours truly.

It will open your $EDITOR in the lower 3rd of your tmux window until you exit it.

Place this in your .bashrc:

`peek() { tmux split-window -p 33 "$EDITOR" "$@" }`

Or place this in your .zshrc (bonus: opens the file in your favorite editor when outside of tmux)
```
peek() {                                         
    if [ -z "${TMUX}"]                           
    then                                         
        $EDITOR $@                               
    else                                         
        tmux split-window -p 33 "$EDITOR" "$@"   
    fi                                           
}                                                
```

Restart your terminal.

Run `peek a_file_you_really_want_to_look_at.txt`

PS! Make sure you have set `export EDITOR=<your editor of choice>`, otherwise the split window will just open then close.

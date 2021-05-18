# Lazy, a tool for running things in idle time

Mostly used to stop CUDA ML model training from making my desktop
unusable. Simply monitors keyboard/mouse idleness using xprintidle,
and pauses the given process using SIGSTOP whenever the machine is in
use (defined as no activity within the last second).

Invoke either with a command,

    lazy train_my_gpu_intensive_model.py

or with a PID of something already running.

    lazy -p 1234

(In PID mode, `lazy` is likely to leave the process paused after
exiting, if cancelled with ^C. Resume it manually with `kill -SIGCONT
$PID`, or `fg` in the shell you originally started it in.)
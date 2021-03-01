# Linux Notes

Keyboard shortcuts
    ctl-A   beginning of line
    ctl-E   end of line
    ctl-K   kill to end of line
    ctl-U   kill from beginning of line
    ctl-Y   yank deleted text back

Repeat the last command but with sudo
    sudo !!

Edit the command line in an editor
    ctrl-x-e

Create a super fast ram disk
    mkdir -p /mnt/ram
    mount -t tmpfs tempfs /mnt/ram -o size=8192M

Execute a command that is not in the history
    Precede the command with a space

Open last command in editor
    fc

Tunnel with ssh
    ssh -L 3337:127.0.0.1:6379 root@emkc.org -N

Quickly create folders
    mkdir -p folder/{sub1,sub2}/{sub1,sub2,sub3}
    mkdir -p folder/{1..10}/{1..10}

Intercept stdout and log to a file
    cat cosmo.txt | tee -a log.txt | cat > /dev/nul

Exit a terminal but leave all processes running
    disown -a && exit

Jobs
    sleep 120 &
    jobs
    fg
    bg
    kill %1

Processes
    sleep 120 &
    killall sleep


    sleep 120 &
    ps


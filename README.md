# Linux Notes

Tips

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

History

    Precede the command with a space and it won't be stored in the history
    
    CTRL-R command  <-- search history for last command usage
    
    export HISTTIMEFORMAT="%d/%m/%y %T "  <-- timestamp history file

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

Directories

    cd ~   <-- home directory
    cd -   <-- last directory
    
Log file tools (works on .gz files)
  
    zcat, zgrep, zless, zdiff
    
Detect if a command modified a file

    D="$(date "+%F %T.%N")"; sleep 0.5; <command>; find . -newermt "$D"
    
Remove a file and make it unrecoverable

    shred -n 100 -z -u filename
    
Finding
    
    function fnd {
        find "$1" -name "$2" 2>&1 | grep -v "Permission denied" | grep -v "Operation not permitted" | grep -v "No such file or directory" | grep -v "Not a directory"
    }
    
    time fnd / george.txt
    
    


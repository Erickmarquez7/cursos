```
erickmain@erickmain:~$ top

top - 18:07:04 up  5:32,  1 user,  load average: 0.52, 0.84, 0.87
Tasks: 262 total,   1 running, 260 sleeping,   0 stopped,   1 zombie
%Cpu(s):  0.0 us,  3.1 sy,  0.0 ni, 96.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   5873.9 total,   1025.6 free,   3041.7 used,   1806.6 buff/cache
MiB Swap:   1402.5 total,   1050.6 free,    351.8 used.   2504.0 avail Mem 

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                  
    890 root      20   0 1104856 145656  89564 S  12.5   2.4   7:14.72 Xorg                                     
   1643 erickma+   9 -11 1425620  25188  19180 S   6.2   0.4   2:01.74 pulseaudio                               
  29109 erickma+  20   0  630476  40436  29544 S   6.2   0.7   0:04.21 mate-terminal                            
  38672 erickma+  20   0   15740   3992   3128 R   6.2   0.1   0:00.01 top                                      
      1 root      20   0  166496  10832   7368 S   0.0   0.2   0:01.44 systemd                                  
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd                                 
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp                                   
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp                               
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 netns                                    
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri              
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.27 kworker/0:1H-events_highpri              
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_percpu_wq                             
     11 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tasks_rude_                          
     ...
```
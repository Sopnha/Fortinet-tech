##Technical Tip: FortiGate VRRP configuration and debug

  This acticle descripbes the Virtual redendancy protocol (VRRP) automatic assignment of available internet protocol (IP) of a router to participating hosts. 

  Simple configure of VRRP protocols

    # config system interface
        edit port2
          set vrrp-virtual-mac enable
            # config vrrp
               edit 1
                set version 2
                set vrgrp 0
                set vrip 0.0.0.0
                set priority 100
                set adv-interval 1
                set start-time 3
                set preempt enable
                set status enable
               next
            end
        next
    end

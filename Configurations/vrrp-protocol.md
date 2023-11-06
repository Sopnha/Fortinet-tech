# Technical Tip: FortiGate VRRP configuration and debug

This acticle descripbes the Virtual redendancy protocol (VRRP) automatic assignment of available internet protocol (IP) of a router to participating hosts. 

**Simple configure of VRRP protocols**

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

**Example for Vrrp configure**

      configure system interface
        edit interface xxx
        set vrrp-virtual-mac enable // enable virtual mac-address
        config vrrp
                edit 5
                    set vrip xx.xx.xx.x   /virtual ip for redundancy
                    set priority 255
                next
            end
            set role lan
            set snmp-index 59
            set interface "port1"
            set vlanid xxx
        next
    end
    

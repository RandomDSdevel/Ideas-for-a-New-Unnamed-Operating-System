# Ideas for a New, Unnamed Operating System

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A list of ideas for potential use in a future operating system I might start as a project one day.  

## Possible Design

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As I've currently started thinking about a potential design, my OS would be divided into multiple, tiered levels of functionality.  I'll describe each one in the following sub-sections.  (Note that tier 0's and tier 1's functionality interleave somewhat, however.)  

### Tier 0&thinsp;—&thinsp;Firmware and Hardware/Platform/System Low-Level Services

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The system architecture would root itself in a [hot-reloadable](https://en.wikipedia.org/wiki/Hot_swapping#Software) and partly [dynamically updatable](https://en.wikipedia.org/wiki/Dynamic_software_updating) virtualizing and [paravirtualizing](https://en.wikipedia.org/wiki/Paravirtualization) UEFI bare-metal (['Type-1'](https://en.wikipedia.org/wiki/Hypervisor#Classification)) hypervisor with the features needed to support:  

 - Nested (and recursive) virtualization (and paravirtualization.)  
 - [Multi-seat virtualization](https://en.wikipedia.org/wiki/Multiseat_desktop_virtualization).  
 - Running guests which _themselves_ support native multi-seat virtualization.  
 - Multi-seat guest environment peer interoperability, including:  
   - Networking pass-through and cross-talk.  
   - Hypervisor-enabled OS and software [KVM](https://en.wikipedia.org/wiki/KVM_switch) passthrough.  
   - Other hardware sharing.  
 - Guest environments capable of [distributed computing](https://en.wikipedia.org/wiki/Distributed_computing).  
 - Run-time provision of UEFI services via either the standard protocols or some layer on top of them to compatible, subscribing client OSes.  

Note that, as a hypervisor and dynamic service provider, this tier continues to run alongside client operating systems, as opposed to shutting down as is conventional, after they boot.  

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

### Tier 1&thinsp;—&thinsp;Unnamed [Exokernel](https://en.wikipedia.org/wiki/Kernel_(operating_system)#Exokernels) (Default Hypervisor Guest)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Atop tier 0 as described above would sit its default guest environment, a similarly hot-reloadable and partly dynamically updatable, paravirtualization-aware exokernel with the features needed to support:  

 - Dynamic run-time consumption of UEFI services from tier 0.  
 - Automatic discovery of any available peer distributed-computing resources and near–zero-configuration use of them in a seamlessly spawnable, free-form network of their host systems whose members could join or leave it at will (with user consent, of course.)  
 - Neighborly cohabitation with any other guest environments running in 'seats' offered concurrently by tier 0.  
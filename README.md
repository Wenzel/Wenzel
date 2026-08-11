<h1 align="center">Hi, I'm Mathieu Tarral</h1>

<p align="center">
  <a href="https://twitter.com/mtarral">
    <img src="https://img.shields.io/badge/-@mtarral-1ca0f1?style=flat-square&labelColor=1ca0f1&logo=twitter&logoColor=white&link=https://twitter.com/mtarral" alt="Twitter">
  </a>
  <a href="https://www.linkedin.com/in/mathieutarral">
    <img src="https://img.shields.io/badge/-mathieutarral-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/mathieutarral" alt="LinkedIn">
  </a>
  <a href="https://github.com/sponsors/Wenzel">
    <img src="https://img.shields.io/badge/Github-Sponsor-EA4AAA?logo=githubsponsors" alt="Github Sponsor">
  </a>
</p>

Security researcher at [Intel](https://www.intel.com) since January 2022, in IPAS since August 2025.

I build **fuzzing and introspection infrastructure for hard-to-reach targets**: firmware, kernels and hypervisors, where snapshotting and hardware-assisted coverage replace the source instrumentation used elsewhere.

Before Intel I worked on virtual machine introspection at ANSSI and F-Secure, and I have been maintaining open-source VMI tooling for Xen and KVM since 2015.

## Repositories

<table>
  <tbody>
    <tr>
        <th align="center">Repository</th>
        <th align="center">Stars</th>
        <th align="center">What it is</th>
    </tr>
    <tr>
        <td colspan="3"><b>Fuzzing</b></td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/IntelLabs/kAFL">kAFL</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/IntelLabs/kAFL?style=social"/>
        </td>
        <td>Snapshot-based, hardware-assisted kernel fuzzer (Intel PT coverage, KVM)</td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/intel/tsffs">TSFFS</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/intel/tsffs?style=social"/>
        </td>
        <td>Coverage-guided fuzzer for firmware and bare-metal targets, built on SIMICS</td>
    </tr>
    <tr>
        <td colspan="3"><b>Virtual machine introspection</b></td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/Wenzel/libmicrovmi">libmicrovmi</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/Wenzel/libmicrovmi?style=social"/>
        </td>
        <td>Cross-platform, hypervisor-agnostic VMI API in Rust, backed by published crates.io bindings for Xen, KVM, Hyper-V and VirtualBox</td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/KVM-VMI/kvm-vmi">KVM-VMI</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/KVM-VMI/kvm-vmi?style=social"/>
        </td>
        <td>VMI on KVM: framework, patched KVM and QEMU forks, and Nitro</td>
    </tr>
    <tr>
        <td colspan="3"><b>Binary analysis</b></td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/Wenzel/checksec.py">checksec.py</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/Wenzel/checksec.py?style=social"/>
        </td>
        <td>Binary hardening scanner for ELF, PE and Mach-O, based on LIEF</td>
    </tr>
    <tr>
        <td colspan="3"><b>Reference</b></td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/Wenzel/awesome-virtualization">awesome-virtualization</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/Wenzel/awesome-virtualization?style=social"/>
        </td>
        <td>Curated list of virtualization resources</td>
    </tr>
    <tr>
        <td colspan="3"><b>Archived</b></td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/Wenzel/pyvmidbg">pyvmidbg</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/Wenzel/pyvmidbg?style=social"/>
        </td>
        <td>Agentless, guest-aware GDB server built on LibVMI</td>
    </tr>
    <tr>
        <td>
            <a href="https://github.com/Wenzel/r2vmi">r2vmi</a>
        </td>
        <td>
            <img src="https://img.shields.io/github/stars/Wenzel/r2vmi?style=social"/>
        </td>
        <td>Hypervisor-level debugger built on radare2 and LibVMI</td>
    </tr>
  </tbody>
</table>

## [OSWatcher](https://github.com/OSWatcher)

Every release of Windows from 95 to 11, and Ubuntu from 6.10 to 25.10, captured and indexed as a single content-addressed graph.

Images are built and captured offline from their qcow2 disks, with no agent running in the guest, then modelled in Neo4j on a git-inspired `Branch -> Commit -> Tree -> Blob` structure. Filesystems, the Windows registry, PDB symbols with reconstructed C structs, DWARF, and syscall tables are indexed as first-class entities, so any two releases can be diffed and any artifact can be traced by hash across every release that ever shipped it.

Seven repositories, Apache 2.0, spanning capture, graph modelling, enrichment, query and UI:

| Repository | Language | Role |
|---|---|---|
| [osw-builder](https://github.com/OSWatcher/osw-builder) | Python | Builds and captures whole sets of OS images |
| [neogit](https://github.com/OSWatcher/neogit) | Python | Content-addressed merkle model on top of Neo4j |
| [oswatcher-plugins](https://github.com/OSWatcher/oswatcher-plugins) | Python | Post-capture enrichment: registry, symbols, DWARF, syscalls, file types |
| [oswatcher-procedures](https://github.com/OSWatcher/oswatcher-procedures) | Java | User-defined Neo4j procedures for fast tree diffing |
| [graphql-api](https://github.com/OSWatcher/graphql-api) | TypeScript | Query surface over the corpus |
| [frontend](https://github.com/OSWatcher/frontend) | TypeScript | Web UI |
| [oswatcher-deploy](https://github.com/OSWatcher/oswatcher-deploy) | Shell | Deployment orchestration |

## Selected talks & writing

- 2020: [FOSDEM](https://archive.fosdem.org/2020/) - [Rustifying the Virtual Machine Introspection ecosystem](https://archive.fosdem.org/2020/schedule/event/rust_vm_introspection/)
  - [Slides](https://docs.google.com/presentation/d/1GVFzqKdMb6OP-jU2JrCyepXsV71yBJ9PJMjVAyM15Gk/edit?usp=sharing)
- 2019: [Hack.lu](https://2019.hack.lu/) - [Leveraging KVM as a Debugging Platform](https://www.youtube.com/watch?v=U-wDpvItPUU)
  - [Slides](https://docs.google.com/presentation/d/1IaMJeBbHmYZMGRvxG8Z7w0c7oBZ2ctH6ZH4CqH4ki5k/edit?usp=sharing)
- 2019: [Insomni'Hack](https://www.insomnihack.ch/conference-2019/) - [Building a Flexible Hypervisor-Level Debugger](https://www.youtube.com/watch?v=-nXY_p8c_bQ)
  - [Slides](https://docs.google.com/presentation/d/1SxLuPEOOSAT3tCXWiurA6PzOLokx82gyaK_ItkBk6Dc/edit?usp=sharing)
- 2018: [Hack.lu](https://2018.hack.lu/) - [Hypervisor-Level Debugger Benefits & Challenges](https://www.youtube.com/watch?v=NnWYT-kCx_s)
  - [Slides](https://docs.google.com/presentation/d/12RXFyKyNoSIh0De95ferPSimK_PvETpwZsGJJJ5r0ZM/edit?usp=sharing)
- 2018: M. Cafasso, M. Tarral, [Designing flexible sandboxing solutions to adapt to new malware trends](https://doi.org/10.1016/S1361-3723(18)30013-7), *Computer Fraud & Security*, 2018(2), 5-9

## Recent Activity

[![Wenzel's GitHub stats](https://github-readme-stats.vercel.app/api?username=Wenzel)](https://github.com/anuraghazra/github-readme-stats)

<!--START_SECTION:activity-->
1. 💪 Opened PR [#379](https://github.com/intel/tsffs/pull/379) in [intel/tsffs](https://github.com/intel/tsffs)
2. 🗣 Commented on [#338](https://github.com/intel/tsffs/pull/338#issuecomment-5180008818) in [intel/tsffs](https://github.com/intel/tsffs)
3. 🗣 Commented on [#347](https://github.com/IntelLabs/kAFL/issues/347#issuecomment-5159491539) in [IntelLabs/kAFL](https://github.com/IntelLabs/kAFL)
4. 💪 Opened PR [#105](https://github.com/OSWatcher/oswatcher-procedures/pull/105) in [OSWatcher/oswatcher-procedures](https://github.com/OSWatcher/oswatcher-procedures)
5. 🎉 Merged PR [#104](https://github.com/OSWatcher/oswatcher-procedures/pull/104) in [OSWatcher/oswatcher-procedures](https://github.com/OSWatcher/oswatcher-procedures)
<!--END_SECTION:activity-->

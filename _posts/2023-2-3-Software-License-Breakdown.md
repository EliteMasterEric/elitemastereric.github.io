---
layout: post
title: A Breakdown on Software Licenses
date: 2023-2-3
---

*With no license, code is "All Rights Reserved" and any other application using your code is committing copyright infringement! So you should choose a license for any code you distribute publically.*

Licenses will additionally protect the copyright holder from damages, and absolve any liability or unstated warranties related to the copyrighted code.

# Copyleft Licenses

- Generally require any changes to the provided source files to be redistributed.
- **Pros:**
  - Encourages contributions to the original project and benefits the open-source community.
  - Prevents massive companies from selling open-source software.
- **Cons:**
  - Discourage (or outright prohibit) use by large entities wanting to use code as a small part of a large closed-source program.
  - Can discourage some developers from using open-source software entirely.

### GNU General Public License (GPL)

- https://opensource.org/licenses/gpl-license
- Any components incorporating the licensed work must also be made open source under GPL.
  - This means no closed-source projects can use GPL code at all!
- Applies recursively even through dependencies.
- The GPL does not require that you distribute your application to the general public.
  - It is entirely legal to sell the application to select customers only, and you only have to distribute your source code only to those parties that have received the binaries.
  - However, those who have received that source code may distribute that source as they please.
- Any application which utilizes the GPL-code is included under the license.
  - This means you can't build the GPL-licensed code into a DLL, then use the DLL in a closed-source application.
- For example, the Haxe compiler (the program that converts Haxe code into code for other languages) is under GPLv2. No closed-source program can use its code.

### GNU Lesser General Public License (LGPL)

- https://opensource.org/licenses/LGPL-3.0
- Closed-source programs may incorporate the licensed work, but must do so with clear separation.
  - For example, making the licensed work into a dynamically linked library (DLL).
- Any modifications to the licensed work itself must be made open-source.
- A core philosophy of LGPL is that end users of a program that incorporates LGPL code should be able to modify the LGPL source, build it, and replace that code with their own.
- For example, libVLC (the backend library powering VLC Media Player) is under the LGPL license.
  - It can be used by other, potentially closed-source programs. but those programs must clearly separate their code from its code, and any modifications to libVLC must be made open-source.

### Affero General Public License (AGPL)

- https://opensource.org/licenses/AGPL-3.0
- Any software incorporating the licensed code must also be made open source under GPL.
  - This means no closed-source projects can use GPL code at all!
- Redefines that a "user" is anyone who accesses a public-facing application.
  - This means that any server-side application that users interact with (even if the binaries are not distributed) are covered under the license.
  - Normal GPL does not require that source code for web servers be redistributed, but AGPL does.

### Mozilla Public License (MPL)

- https://opensource.org/licenses/MPL-2.0
- Any modifications to the licensed code must be publicly distributed, but closed-source projects can incorporate them.
- Licensing is by-file; for example, a project can contain some MPL files and some files under another license, but any changes to the MPL files must be made public.
- Compatible with GPL
  - This means an open-source project may use some code licensed under GPL and other code licensed under MPL.
  -

# Permissive Licenses

- Generally does not require changes to the provided source files to be redistributed.
- **Pros**:
  - Encourages use of the components by the wider community (for example, a commercial video game can use the library).
- **Cons**:
  - Allows corporations to use the code without contributing (but not without credit).

### MIT License

- https://opensource.org/licenses/MIT
- MIT License is the most commonly used permissive license.
- Closed-source software may use the provided code, as long as the original license is distributed.
  - A license file containing something like "Contains code from libname, which is under the MIT License" is generally sufficient.
- For example, the Haxe standard libraries are under the MIT License. Any program may use its code (with proper credit), even if they are closed source.

### Apache License

- https://opensource.org/licenses/Apache-2.0
- Similar to the MIT license (code may be used with attribution) with several caveats:
  - Explicit clauses relating to software patents.
    - Patent rights held by the copyright holder which are contained in the licensed code are explicitly granted, but the patent grant is revoked in the event that
  - Strict rules around usage of trademarks related to the software module.
- The Apache License is widely used for open source work performed by large companies such as Google.

### BSD License (0-clause)

- https://opensource.org/licenses/0BSD
- There are actually several different BSD licenses available, with increasingly restrictive terms.
- The 0-clause license is basically identical to the Unlicense, which grants the material to the public domain.

### BSD License (1-clause)

- https://opensource.org/licenses/BSD-1-Clause
- Requires redistributions of the source code to include a license disclaimer.
- Does not require binary distributions to include the license disclaimer, unlike BSD-2 or MIT.

### BSD License (2-clause)

- https://opensource.org/licenses/BSD-2-Clause
- Requires redistributions of binaries or source code to include a license disclaimer.
- The 2-clause license is basically idential to the MIT License, which requires attribution for works.
- MIT and BSD are generally considered compatible.

### BSD License (3-clause)

- https://opensource.org/licenses/BSD-3-Clause
- On top of BSD-2, states that use of the software may not be used for advertising (Made with Libname!) without explicit written permission.

### Unlicense

- The source code is released into the public domain.
- There are no terms for the code, and the code may be redistributed without source and even under different license terms.

# Art/Music Licenses

See here for info on art and music licenses: https://creativecommons.org/about/cclicenses/

# Additional Notes/Q&A

- Can software be open-source but also private?
  - YES. Open source doesn't refer to how the code is distributed, but the _RIGHTS_ you have once you receive it.
  - When "the changes must be made open source" is stated above, this only applies if "
  - It is entirely legal to sell the application to select customers only, and you only have to distribute your source code only to those parties that have received the binaries.
- What does it mean for software to be closed-source?
  - Code under a closed-source/properietary license may be associated with "trade secrets" or "proprietary material" sections of non-disclosure agreements, and those who redistribute it may violate the owner's copyrights and be sued.
- What happens if someone violates these terms?
  - If an entity is discovered to have violated the terms of a software license, they may be sued by the owner of that licensed code for copyright infringement.
- What does it mean for one license to be compatible with another?
  - Two software licenses are compatible if a piece of software which combines them (i.e. utilizes modules of code under each license) may be legally distributed under that license.
  - For example, if the other license and the GNU GPL are compatible, you can combine code released under the other license with code released under the GNU GPL in one larger program.
  - GPL code is generally compatible with permissive code, but incompatible with non-permissive code (such as that which requires a commercial license to use or distribute).
- Can I change the license of my code?
  - The answer can be complicated. If you own all the code in the relevant repository, you may do so as you like.
  - If you did not write all of the code in the repository, you do not own those chunks of code. The code which other users contributed code via pull requests are the partial copyright owners of that chunk of code. You will have to either ask permission to update the license or refactor the code to remove their contributions.
  - To prevent future issues, you may require contributors sign a Contributor's License Agreement (CLA), which waives all ownership of a piece of code and grants it to you. This is usually only relevant for commercial programs or libraries managed by a large company.

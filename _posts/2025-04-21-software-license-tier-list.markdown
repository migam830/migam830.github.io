---
layout: post
title: Software license tier list
---
I have seen many tier lists but haven't seen any software license ones. This is probably because no one has ever had enough interest in software licenses to make a tier list. I am fascinated by software licenses, though, so here is a tier list ranking them.

Obviously, this is my opinion and this isn't objective in any way.

Also, there are hundreds of software licenses (anyone can write their own license), I am just focusing on the most common ones.

I am not a lawyer, this is not legal advice.

Here is my tier list:

| <span style="color:red">S</span> | `GPL` `AGPL` |
| <span style="color:orange">A</span> | `MIT` `LGPL` `CC0` `0BSD`  `Apache` `MPL` |
| <span style="color:gold">B</span> | `WTFPL` `BSD-2-Clause` `BSD-3-Clause` `BSL` |
| <span style="color:green">C</span> | `Unlicense` `BSD-4-Clause` |
| <span style="color:turquoise">D</span> | `SSPL` |
| <span style="color:purple">F</span> | `Closed Source` `License Change` |

## Clarification
* `GPL` refers to `GPL-3.0-only` 
* `AGPL` refers to `AGPL-3.0-only`
* `LGPL` refers to `LGPL-3.0-only`
* `CC0` refers to `CC0-1.0`
* `Apache` refers to `Apache-2.0`
* `MPL` refers to `MPL-2.0`
* `BSL` refers to `BSL-1.0`
* `SSPL` refers to `SSPL-1.0`
* `Closed Source` refers to any software license where the source code cannot be accessed by everyone who can access the object code
* `License Change` refers to swapping the license for your software from one that meets the [open source definition](https://opensource.org/osd/) to one that doesn't

All other licenses in the tier list are referenced by their [SPDX identifiers](https://spdx.org/licenses/).

## Explanation
`GPL` and `AGPL` are my favourite licenses. They allow the user to do essentially what they want with the software but ensure they ensure the same license is used. This maximises freedom and makes sure big corporations can't publish a modified version of your code without also providing the source code. I use these licenses for almost all the software I make. All these reasons are why they go in S tier.

The `MIT` license is probably the most popular license for people just starting out to write software and is recommended by many sites. I think it is a good license. It meets the criteria of both [open source](https://opensource.org/osd/) and [free software](https://www.gnu.org/philosophy/free-sw.en.html/) and places no restrictions on what you can use the software for. The only condition is you have to include a copy of the license and copyright notice in all copies of the software (regardless of whether the software is modified). The reason I didn't put the `MIT` license in S tier is because its permissive nature allows people and companies to take your software, make a closed source version and give nothing back. You might not take issue with that and that is fine. Personally, however, this annoys me so I prefer `GPL`. That is why `MIT` goes in A tier.

The `BSL` (Boost Software License) is similar to the `MIT` license except you only need to include the license and copyright notice if you are distributing the source code and doesn't require this for object code. I am putting this license in B tier because it is very similar to the `MIT` license but I think it is easier to simply require the copyright notice for all copies of the software. Only requiring this for source code is probably easier to enforce and slightly more convenient but giving attribution is not difficult so I don't see why you shouldn't just use `MIT`.

The `Apache` license is similar to the `MIT` license except it expressly grants a patent license and requires you to state the changes you made. `Apache` is a very popular license but I am less familiar with it than `GPL` or `MIT`. Apache is a popular, permissive license and I am putting it in A tier.

The `LGPL` license is similar to `GPL` except it allows people to use the software in non-GPL code as a library. This is useful if you want the library itself to always be open source but require it to be used in projects that are not open source. I wouldn't use this unless there was a good reason why the regular `GPL` wouldn't work so I am putting the license in A tier.

The `MPL` is very similar to the `LGPL`. It is also a weak copyleft license but talks about use in non-MPL code in terms of files rather than libraries. It is compatible with the `GPL`. I am not too familiar with this license but it is very similar to `LGPL`. I am putting this license in A tier since it is almost the same as `LGPL` in the same tier.

`CC0` and `Unlicense` are both licenses with no conditions whatsoever that aim to put your work in the public domain. However, the `Unlicense` probably won't hold up in countries that don't have the notion of 'public domain' which could mean the license isn't enforcible. This is why I put `Unlicense` in C tier. `CC0` is similar, but it works a bit differently. It puts your work in the public domain if such a notion exists in the applicable jurisdiction. If there isn't, `CC0` grants you as many rights as the jurisdiction will allow. This is why I think `CC0` is a better public domain license and I put it in A tier.

The `WTFPL` or the "Do What The Fuck You Want To Public License" is a public domain equivalent license. The rights this license gives you is probably self-explanatory. This license is probably not the best choice for your software. It hasn't been tested in court to the best of my knowledge and doesn't include a no-warranty disclaimer (although you can add one yourself). Also, I have no idea how the license's only clause "You just DO WHAT THE FUCK YOU WANT TO" would be interpreted in a legal context. On the other hand, it's funny so it gets B tier.

There are many licenses which get referred to as "the BSD license". These are similar but have some important differences. The `BSD-2-Clause` license is effectively the same as the `MIT` license. The `BSD-3-Clause` license is the same as the 2 clause one but has a clause prohibiting the promotion of derived products without permission. I have put `BSD-2-Clause` and `BSD-3-Clause` in B tier since they are very similar to `MIT`. The reason I put them lower than `MIT` is because the different variants can be confusing. I put `BSD-4-Clause` in C tier since it also has a clause requiring all advertisements to acknowledge the original creator. This isn't too big a deal but makes the license incompatible with the `GPL`.

`0BSD` is a public domain equivalent license which has no conditions in it. It's like `WTFPL` but more serious. I put `0BSD` in A tier since it gives users almost the same rights `CC0` without actually releasing the work into the public domain.

`SSPL` is a source-available license based on the `AGPL`. It is not an open source license due to extra restrictions it places. It says anyone that provides `SSPL` code as a service has to make the source code of their entire tech stack available. The restrictions don't seem terrible, but they could be very hard to comply with. The main reason I put this license in D tier is because this license is often used to relicense software that was previously open source. Since software licensed under the `SSPL` is not open source, relicensing can be extremely problematic to people who were reliant on the software being open-source.

I have obviously put `Closed Source` in F tier. This is because such software gives the user no freedom and can be used to lock the user into a specific company's ecosystem. I am not completely against all closed source software in existence, but I would always use an open source alternative to something closed source if that is possible. Licenses in all the other tiers are definitely better than closed source since they all provide the user at least some freedom.

I have also included `License Change` in my tier list and put it in F tier. This is when a company develops a piece of software and releases it as open source for a while, only to change the license to a source-available or closed source one later on down the line. This can be a huge problem for people and developers who relied on the open source software. Yes, users can continue to use the open source versions of the software as long as they want, but they won't get any updates unless they switch to the other license or someone in the community forks the software. Some examples of where this has happened are Terraform and Redis.

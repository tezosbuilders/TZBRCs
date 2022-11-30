---
tzbrc: 1
title: TZBRC Purpose and Guidelines
status: Draft
type: Meta
author: Göran Sandström (@veqtor)
created: 2022-11-30
---

## What is an TZBRC?

TZBRC (tez-bee-aar-see) stands for Tezos Builders Request for Comments, which are documents that describe standards for smart contracts and APIs proposed by members and outside collaborators

## TZBRC Rationale

We intend TZBRCs to be the primary mechanisms for proposing new standards, for collecting community technical input on an issue, and for documenting the design decisions. Because the TZBRCs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

## What is a TZBRC?

A TZBRC is a design document providing information to the Tezos community, describing a feature for Tezos or its processes or environment, and supporting the formal protocol governance process.

The role of a TZBRC is purely supplementary, hortative, or descriptive; the Tezos protocol is defined at all times by the implementation whose hash has been incorporated into the current protocol ID and approved by the Tezos quorum. TZBRCs can and will diverge from and contradict one another, so long as all
active TZBRCs remain compatible with the current protocol.

A TZBRC should contain a concise technical specification and rationale which unambiguously articulates what the proposal is, how it may be implemented, and why the proposal is an improvement. A TZBRC should additionally contain an FAQ which documents, compares, and answers alternative options, opinions, and objections.

## Rationale

We intend TZBRCs to be one possible mechanism for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into decentralized applications built on Tezos. TZBRCs are maintained as text files in a versioned repository; their revision history is a historical record of the feature proposal.

For Tezos developers, TZBRCs can be a useful way to generate feedback, clearly communicate functionality to users, and track the progress of their work. Maintainers of Tezos tools and libraries can list the TZBRCs that they have implemented, which can give the community a convenient way to know the current status of a given project.

It is highly recommended that a single TZBRC contain a single key proposal or new idea corresponding to its type. A change to a single library or application may not require an TZBRC, whereas a change that affects multiple independent libraries or applications probably does.

A TZBRC must meet certain minimum criteria, which may change depending on the TZBRC type. Some TZBRC types may require an attached reference implementation of the proposed improvement. Other TZBRC types may require two independent implementations. If so, the associated software should be of minimal possible complexity and be focused primarily on illustrating the contents of the single proposal to which it is attached. Reference implementations should show evidence of correctness, ideally via formal methods, but at minimum via comprehensive testing.

Whenever possible, TZBRCs and documents should refer to relevant TZIPs if available. TZBRCs can be seen as informal "proto-TZIPs".


### Status Description

A TZBRC can have the following statuses:


| Status             | Actor    | Description                                                                                                                            | Action(s) to get that Status                                      | Next Status(es)         |
| :----------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------- | :---------------------- |
| `Work In Progress` | Author   | This covers the initial work being done to create the TZBRC and its accompanying resources                                              | 1. Author submits a MR to:<br/>&nbsp;&nbsp;- reserve a TZBRC number, say *xxx*, in the [README](/README.md)<br/>&nbsp;&nbsp;- add the *Work In Progress* status in the README<br/>&nbsp;&nbsp;2. Author creates a new branch, *tzbrc-xx*, to work on it      | Draft, Withdrawn |
| `Draft`            | Author   | The TZBRC is now in good shape, and is ready to be shared with the community to get iterative feedback                                  | 1. Author submits a MR from the *tzbrc-xxx* branch, including the status change to *Draft* in the README<br/>2. Reviewer merges the MR to *master* | Submitted, Withdrawn |
| `Withdrawn`        | -        | The authors decide that the TZBRC is no longer needed, or the reviewers decide to reject it (e.g. for non-compliance)                   | 1. Author or Reviewer closes the *tzbrc-xxx* branch<br/>2. Author or Reviewer updates the TZBRC and README with the *Withdrawn* status                       | -                    | 
| `Submitted`        | Reviewer | The TZBRC has been approved by the community and is submitted to the reviewers                                                          | Author updates the TZBRC and README with the *Submitted* status    | Final, Draft, Withdrawn |
| `Final`            | Reviewer | The TZBRC has been approved by the reviewers                                                                                            | Reviewer updates the TZBRC and README with the *Final* status      | Deprecated, Superseded, Promoted  |
| `Deprecated`       | -        | The TZBRC is no longer valid and shouldn't be used anymore. It is kept here as a reference but hasn't been superseded by any newer TZBRC | Reviewer updates the TZBRC and README with the *Deprecated* status | -                       |
| `Superseded`       | -        | The TZBRC is no longer valid, but unlike the *Deprecated* status, this TZBRC has been superseded by a newer TZBRC                         | Reviewer updates the TZBRC and README with the *Superseded* status | -                       |
| `Promoted`       | -        | The TZBRC is no longer valid because it has been promoted to a TZIP                         | Reviewer updates the TZBRC and README with the *Promoted* status | -                       |


### TZBRC Authors

Once the authors are happy with the initial work on their TZBRC, they will move its status from *Work In Progress* to *Draft*. At that point, the authors should solicit feedback from the Tezos Builders community before submitting the TZBRC to the reviewers. As prior work on the same or similar topics may not be immediately apparent or accessible from publicly available information,  nviting community advice can both save time and effort, and result in a stronger proposal.

Once the authors have gotten enough feedback from the community and updated the TZBRC accordingly, they will move its status to *Submitted* for the reviewers to review.

### TZBRC Reviewers

Once the TZBRC moves to *Submitted*, the reviewers will:
- Read the TZBRC to check if it complies with all relevant standards articulated in this document and elsewhere, both global TZBRC standards and those particular to the TZBRC type.
- Edit the TZBRC for prose (spelling, grammar, sentence structure, etc.), markup (GitHub Flavored Markdown).
- Review any accompanying resources, such as implementations, proofs, papers, links, etc.
- When relevant, determine whether the FAQ fairly expresses and responds to criticisms of the proposal.

If the TZBRC does not meet the standards, the reviewers will send it back to *Draft*, with specific instructions, so the authors can update it. This process may repeat as many times as necessary. The reviewers may additionally refer the TZBRC to outside reviewers with relevant knowledge. Reviewers may also outright reject a TZBRC submission that is unsuitable for review or is otherwise non-compliant with the standards outlined in relevant active TZBRCs.

Should the reviewers approve the TZBRC, they will:

- Merge the corresponding merge request. The TZBRC reviewers have sole ownership over the GitHub repository.
- Coordinate any further steps with the TZBRC authors, as required by the specific TZBRC type.


## TZBRC Sections

Each TZBRC should have the following sections:

- **Header Preamble**: Headers containing metadata about the TZBRC, including the TZBRC type, a short title, and the author details.
- **Summary**: Provide a simplified and layman-accessible explanation of the TZBRC.
- **Abstract**: A short (200-500 word) but comprehensive description of the issue being addressed and the proposed solution.
- **Motivation**: It should clearly explain why the existing implementation is inadequate to address the problem that the TZBRC solves.
- **Specification**: The technical specification should describe the syntax and semantics of any new feature.
- **Rationale**: The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should
describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence
of consensus within the community, and should discuss important objections or concerns raised during discussion.
- **Backwards Compatibility**: All TZBRCs that introduce backwards incompatibilities or supersede other TZBRCs must include a section describing these incompatibilities, their severity, and solutions.
- **Test Cases**: Test cases for an implementation are strongly recommended as are any proofs of correctness via formal methods.
- **Implementations**: Any implementation must be completed before the TZBRC is given the status Submitted, but is not mandatory in *Work In Progress* and *Draft* status.
- **Appendix**: A list of references relevant to the proposal.
- **Copyright**: All TZBRCs must be in the public domain, or under a permissive license substantially identical to placement in the public domain. See the bottom of this TZBRC for an example copyright waiver.


## TZBRC Formats and Templates

TZBRCs should be written in [Markdown] format. TZBRC templates are available in the [Templates](/templates) folder.
Additionally, the authors agree to follow and enforce the TZIP Code of Conduct, described in [TZIP-3].


## TZBRC Header Preamble

Each TZBRC must begin with an RFC 822 style header preamble, preceded and followed by three hyphens (`---`). The headers must appear in the following order.

- `tzip:` TZBRC number. The number should be requested via a merge request as soon as the TZBRC is in *Work In Progress* status
- `title:` A short descriptive title, maximum 44 characters. If the TZBRC has a *name* (see [TZIP-2]), then it is added as a title prefix (e.g. *TZBFA1 - Abstract
Ledger*), again, prefixing with TZB to avoid collisions
- `author:` Name(s) of author(s), ideally with their username(s) or email address(es). Examples: *John Doe*, *John Doe (@username)*, *John Doe
&lt;address@dom.ain&gt;*
- `gratuity:` Optional. A Tezos address controlled by an author capable of receiving gratuities from grateful Tezos users
- `discussions-to:` Optional. A url pointing to the official discussion thread
- `status:` Can be: Work In Progress | Draft | Withdrawn | Submitted | Deprecated | Superseded | Promoted
- `type:` TZBRC type, same as TZIP type as defined in [TZIP-2]
- `created:` Date the TZBRC was created, format yyyy-mm-dd
- `requires:` Optional. TZBRC numbers, representing TZBRCs that this TZBRC depends on
- `replaces:` Optional. TZBRC numbers, representing the TZBRCs the current TZBRC is replacing
- `superseded-by:` Optional. TZBRC numbers, representing the TZBRCS replacing the current TZBRC
- `promoted-tzip:` Optional. TZIP number this TZBRC has been promoted to
Headers that permit lists must separate elements with commas.


## Transferring Primary Authorship

It occasionally becomes necessary to transfer primary authorship of a TZBRC to a new primary author. In such case, the previous primary author will remain as a co-author or an author emeritus. This can occur by unilateral decision of the primary author, via a request of a co-author, or in extraordinary circumstances via a unilateral decision from the TZBRC reviewers. 

## History

This document was derived from Tezos's [TZIP-1] which was in turn derived from Ethereum's [EIP-1] which was in turn derived from Bitcoin's [BIP-0001] written by Amir Taaki and Python's [PEP-0001], written by Barry Warsaw, Jeremy Hylton, and David Goodger. 
None of the authors of [TZIP-1], [EIP-1], [BIP-0001], or [PEP-0001] are responsible for its use in the Tezos Builders Request for Comments Process, and should not be bothered with technical questions specific to TZBRCs.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

[TZIP-1]: https://tzip.tezosagora.org/proposal/tzip-1/
[TZIP-2]: https://tzip.tezosagora.org/proposal/tzip-2/
[TZIP-3]: https://tzip.tezosagora.org/proposal/tzip-3/
[Markdown]: https://docs.gitlab.com/ee/user/markdown.html
[EIP-1]: https://github.com/ethereum/EIPs
[BIP-0001]: https://github.com/bitcoin/bips
[PEP-0001]: https://www.python.org/dev/peps/
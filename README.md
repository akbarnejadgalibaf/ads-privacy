Bid request signal experiments
==============================

[Real-time bidding](https://en.wikipedia.org/wiki/Real-time_bidding) is a
technology that allows advertisers to buy and content creators to sell ad
inventory on a per-impression basis via instantaneous auctions, with multiple
buying platforms competing. RTB helps advertisers and publishers to optimally
allocate advertising inventory and assign a fair value to each impression.

In order to further improve user privacy protections, the Google RTB team is
starting to consider how
[Chrome Privacy Sandbox](https://www.chromium.org/Home/chromium-privacy/privacy-sandbox)
ideas can be applied to RTB. We’d like to experiment with design changes to the
RTB interface between advertising exchanges and bidders to enable publishers to
choose stronger user privacy protections, while keeping RTB an effective
channel to reach audiences and to monetize publisher inventory. 

For example, real-time bidding could support targeting advertiser audiences via
segments that refer to groups of many users sharing common interests or
characteristics rather than a pseudonymous identifier referring to one user.
Such aggregated audience segments could be provided by different sources,
including an advertising exchange, a publisher, an advertiser, or a browser
(see [Federated Learning of Cohorts](https://github.com/jkarlin/floc)).
Exchanges could offer a uniform RTB interface for aggregated audience targeting
to bidders regardless of the data source.

For remarketing – advertising based on past visits to advertiser web sites – 
exchanges could experiment with concepts described in the
[TURTLEDOVE](https://github.com/michaelkleber/turtledove) proposal. Exchanges
can explore the separation between contextual and user interest components in
the RTB data flow, along with hosting the ad selection logic that needs access
to both components (for instance, brand safety checks for a product remarketing
ad) in a sandbox. In addition, exchanges could design a consistent RTB
interface for remarketing with improved privacy protections working across
diverse environments, including browsers that support
[on-device ad selection](https://github.com/michaelkleber/turtledove)
and platforms that use pseudonymous resettable identifiers for advertising.

Advertising exchanges can also apply the idea of a
[Privacy Budget](https://github.com/bslassey/privacy-budget) to improve the RTB
interface privacy protections and reduce or obviate the reliance on such
high-entropy fields as IP address and user agent (some exchanges may already be
limiting the entropy, for example, by truncating the IP address in the bid
request). With constraints imposed by the privacy budget, a given bid request
would not provide information about a device that may allow one to indirectly
identify a specific user or a very small group of users, and instead offer
fields that enable targeting by sufficiently coarse-grained geolocation or
device and browser type. 

For use cases such as non-human traffic and abuse detection, where access to
the signals from the device continues to be vital to prevent fraudulent
activity, the RTB ecosystem would benefit from being able to ensure buyer’s
confidence in the inventory sold programmatically while minimizing the
sharing of the information about the user. We propose to experiment with
approaches such as the
[Trust Token API](https://github.com/WICG/trust-token-api), which allow trust
token issuers – i.e. sites with user interactions that can indicate high
likelihood of real and valid users – to share that knowledge with other parties
without increasing the ability to track users across sites.

We plan to evaluate the viability of these and other proposals via small-scale
real-world experiments conducted by exchanges and bidders. We welcome
advertising industry partners to provide
[input](https://github.com/google/rtb-experimental/issues) to these RTB
experiments that minimize user data sharing and better protect user privacy.

License
-------

Copyright 2020 Google, Inc.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.


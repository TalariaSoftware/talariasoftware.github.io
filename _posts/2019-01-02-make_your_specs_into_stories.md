---
title: Make Your Specs Into Stories
description: Use the power of narrative to make your tests easier to understand.
image: /images/articles/woman_leaving_helicopter.jpg
published_at: Jan 2, 2019 1:30 pm Pacific Time
---

There are a lot of moving parts at Voom; riders, helicopters, and helipads
interact in complex ways to ensure the effective operations. As a result, we
often need a lot of setup when running our tests.

A large test setup can look like a random collection of unrelated facts. They
are difficult to read, difficult to understand, and difficult to remember.
Because humans are hard-wired to think in narrative, crafting test setup as
stories makes them easier to read, easier to understand, and easier to
remember.

Using stories, instead of mere collections of facts can make your
specifications easier to read and understand.

## An example set of facts

> Individual one traveled from location one to location two at time zero.
> Individual one traveled from location two to location one at time one.
> Individual one traveled from location one to location three at time two.
> Individual one traveled from location three to location one at time three.

Without looking back at the example try to answer the following questions:

- How many times did individual one arrive at location one?
- Which location did individual one go to first - location three or location two?
- Where did individual one end up?
- Did you have to think a little bit to answer any of the questions? Were you unsure about the answer to any of the questions?

## An example story

> Adriana went to work at nine and came home at five. Then she went to
a concert at seven and came home at eleven.

<figure>
  <img class='maxw-mobile-lg' src='/images/articles/woman_leaving_helicopter.jpg' alt='woman leaving helicopter'>
  <figcaption class='font-body-3xs'>
    Our fictional Adriana arriving at work
  </figcaption>
</figure>

It’s not exactly Hemingway, but notice how much easier and more enjoyable it is
was to read.

Without looking back at the story, answer these questions:

- How many times did Adriana go home?
- Did Adriana go to the concert first or to work first?
-  Where did Adriana end up?

Did you get all of the questions right? Did the answers come to you easily and effortlessly?

## RSpec facts

We can create a similar effect in RSpec. Here is a test setup that is a collection of facts:

```ruby
let(:rider1) { FactoryBot.create(:rider) }
let(:location1) { FactoryBot.create(:location) }
let(:location2) { FactoryBot.create(:location) }
let(:location3) { FactoryBot.create(:location) }
let!(:journey1) { FactoryBot.create(:journey, rider: rider1, origin: location1, destination: location2, time: Time.at(0)) }
let!(:journey2) { FactoryBot.create(:journey, rider: rider1, origin: location2, destination: location1, time: Time.at(1)) }
let!(:journey3) { FactoryBot.create(:journey, rider: rider1, origin: location1, destination: location3, time: Time.at(2)) }
let!(:journey4) { FactoryBot.create(:journey, rider: rider1, origin: location3, destination: location1, time: Time.at(3)) }
```

Can you tell if these expectations are correct without looking back at the setup?

```ruby
specify { expect(location1.arrivals.count).to eq(2) }
specify ( expect(journey3).to be_later_than(journey1) }
specify { expect(rider1.current_location).to eq(location1) }
```

## RSpec story

Here is an analogous setup that is crafted into a story.

```ruby
let(:adriana) { FactoryBot.create(:rider) }
let(:home) { FactoryBot.create(:location) }
let(:work) { FactoryBot.create(:location) }
let(:concert) { FactoryBot.create(:location) }
let!(:to_work) { FactoryBot.create(:journey, rider: adriana, origin: home, destination: work, time: Time.parse('9am')) }
let!(:from_work) { FactoryBot.create(:journey, rider: adriana, origin: work, destination: home, time: Time.parse('5pm')) }
let!(:to_concert) { FactoryBot.create(:journey, rider: adriana, origin: home, destination: concert, time: Time.parse('7pm')) }
let!(:from_concert) { FactoryBot.create(:journey, rider: adriana, origin: concert, destination: home, time: Time.parse('11pm')) }
```

Can you easily tell that these expectations are correct?

```ruby
specify { expect(home.arrivals.count).to eq(2) }
specify ( expect(to_concert).to be_later_than(to_work) }
specify { expect(adriana.current_location).to eq(home) }
```

## How this works

Stories are facts and occurrences fleshed out with characters, causality and
emotional response. An indistinct person traveling from one indistinct location
to another indistinct location is very different from Adriana returning home
from the awesome concert she went to after a long day at work.

Our minds are hard wired to think in about these things (characters, causality,
and emotions). By writing our specs to take advantage of this, we can enlist
much more powerful and primal parts of our mind to help others understand what
we have written.

## Caveats

Don’t overdo it. Adding a lot of information in order to turn your test into
a narrative will actually make the tests more complicated and more difficult to
read. It doesn’t take a lot of information to create a narrative.

Don’t do this instead of making things simpler. A better solution to
complicated test setup is to refactor the code. Often that means simplifying
the business rules and domain model. Adding a more explicit narrative should be
done in addition to that when it helps.

## Conclusion

Sprinkling our specifications with narratives is one way to make your codebase
clear, easy to read, easy to maintain, and enjoyable to work with.

# Creative Test Case Scenarios

## 1. Elevator System
**Introduction:** Testing an elevator involves evaluating its mechanical, electrical, and software components. Key focus areas include safety, usability, performance, and fault tolerance.

| #  | Test Case Description                                | Steps to Execute                        | Expected Result                                | Priority |
|----|------------------------------------------------------|-----------------------------------------|------------------------------------------------|----------|
| 1  | Verify elevator moves between floors correctly       | Press floor button                      | Elevator reaches the selected floor            | High     |
| 2  | Verify doors open and close fully                    | Wait after reaching floor               | Doors open/close completely                    | High     |
| 3  | Verify elevator stops at requested floors            | Select multiple floors                  | Elevator stops at each selected floor          | High     |
| 4  | Verify emergency button functionality                | Press emergency button                  | Alarm triggers or connects to help desk        | High     |
| 5  | Verify behavior when overloaded                      | Add weight over limit                   | Elevator doesn’t move, triggers alert          | High     |
| 6  | Verify elevator resets after power failure           | Simulate power failure                  | Elevator resets to default state               | Medium   |
| 7  | Test multi-floor requests                            | Press different floor buttons           | Elevator visits floors in order                | Medium   |
| 8  | Verify door obstruct handling                        | Block door during closing               | Door reopens automatically                     | High     |
| 9  | Verify accurate floor display                        | Travel floors                           | Display matches actual floor                   | Medium   |
| 10 | Verify floor audio announcement                      | Travel floors                           | Correct floor announced                        | Low      |
| 11 | Test fire alarm response                             | Trigger fire alarm                      | Elevator moves to ground and halts             | High     |
| 12 | Verify restricted access to service floors           | Try accessing restricted floor          | Access denied or prompts for keycard           | Medium   |
| 13 | Test pressing same button repeatedly                 | Press same floor multiple times         | No additional action                           | Low      |
| 14 | Verify internal lighting                             | Enter elevator                          | Lights are functional                          | Low      |
| 15 | Measure elevator speed                               | Time floor-to-floor movement            | Speed within limits                            | Medium   |
| 16 | Test noise/vibration                                 | Ride elevator                           | Smooth movement with minimal sound             | Low      |
| 17 | Test manual door force                               | Try forcing doors open                  | Elevator stops and alarm triggers              | High     |
| 18 | Cancel floor request                                 | Press cancel after selecting a floor    | Request is cancelled                           | Low      |
| 19 | Auto-return on idle                                  | Leave elevator idle                     | Returns to base floor                          | Medium   |
| 20 | Test alarm & intercom functionality                  | Press alarm and intercom                | Both trigger appropriate responses             | High     |

## 2. Pen
**Introduction:** A pen is a common writing instrument. Testing includes ink flow, usability, durability, and environmental tolerance.

| #  | Test Case Description                          | Steps to Execute             | Expected Result                      | Priority |
|----|------------------------------------------------|------------------------------|--------------------------------------|----------|
| 1  | Verify pen writes on paper                     | Write on normal paper        | Smooth and consistent ink flow       | High     |
| 2  | Test ink flow consistency                      | Draw long line               | Ink does not skip or fade            | High     |
| 3  | Write at different angles                      | Tilt pen at various angles   | Ink continues to flow                | Medium   |
| 4  | Check ink leakage at high temp                 | Expose to heat               | No ink leakage                       | Medium   |
| 5  | Test cap functionality                         | Open and close cap           | Cap fits well without damage         | Low      |
| 6  | Immediate ink flow                             | Start writing without shaking| Ink flows instantly                  | Medium   |
| 7  | Long duration writing                          | Write continuously           | Ink lasts as expected                | Medium   |
| 8  | Ink drying speed                               | Swipe after writing          | Dries quickly without smudge         | Medium   |
| 9  | Material durability                            | Apply pressure               | Pen does not break easily            | Low      |
| 10 | Check clip durability                          | Attach repeatedly to pocket  | Clip does not break                  | Low      |
| 11 | Ink behavior on different papers               | Write on glossy/textured     | No bleeding or smudge                | Medium   |
| 12 | Refill mechanism (if refillable)               | Refill cartridge             | Refill is smooth and secure          | Medium   |
| 13 | Ink odor                                        | Smell pen                    | No unpleasant odor                   | Low      |
| 14 | Write on vertical surface                      | Use on wall/whiteboard       | Writes consistently                  | Medium   |
| 15 | Grip with wet hands                            | Use with wet fingers         | No slipping, continues to write      | Low      |
| 16 | Drop test                                       | Drop from desk               | Pen survives fall                    | Medium   |
| 17 | Branding durability                            | Use over time                | Branding remains visible             | Low      |
| 18 | Environmental test                             | Cold/hot environment         | Works in all conditions              | Medium   |
| 19 | Balanced weight distribution                   | Write long paragraph         | No strain, balanced feel             | Low      |
| 20 | Idle usage test                                | Leave unused, then write     | Starts writing without issue         | Medium   |

---

## 3. Cup/Glass
**Introduction:** Testing a cup involves validating its design, durability, heat resistance, usability, and handling of liquids.

| #  | Test Case Description                         | Steps to Execute                       | Expected Result                              | Priority |
|----|-----------------------------------------------|----------------------------------------|----------------------------------------------|----------|
| 1  | Check if cup holds liquid without leaking     | Fill with water                        | No leakage or seepage                        | High     |
| 2  | Verify handle durability                      | Hold with full content repeatedly      | Handle remains intact                        | High     |
| 3  | Test heat resistance                          | Pour hot liquid                        | Cup does not crack or deform                 | High     |
| 4  | Check for cracks or manufacturing defects     | Inspect visually                       | No visible cracks or sharp edges             | Medium   |
| 5  | Cold liquid test                              | Fill with ice or cold water            | No cracks or sweating (condensation control) | Medium   |
| 6  | Verify dishwasher safety                      | Wash in dishwasher                     | No damage or fading                          | Medium   |
| 7  | Microwave safe test (if applicable)           | Heat in microwave                      | Cup withstands microwave conditions          | High     |
| 8  | Drop test                                     | Drop from standard height              | No shattering or breakage                    | High     |
| 9  | Test with acidic liquids                      | Pour juice, vinegar                    | No chemical reaction or staining             | Medium   |
| 10 | Check balance on flat surface                 | Place on table                         | Cup stands upright without wobbling          | Medium   |
| 11 | Spill test with movement                      | Move tray or tilt slightly             | Cup doesn’t tip easily                       | Medium   |
| 12 | Grip comfort test                             | Hold with one hand                     | Comfortable grip                             | Low      |
| 13 | Fill level marking accuracy (if present)      | Fill to marked level                   | Matches actual capacity                      | Low      |
| 14 | Test labeling durability (design/print)       | Wash multiple times                    | Print remains intact                         | Low      |
| 15 | Odor absorption test                          | Use with various drinks                | No lingering smell                           | Low      |
| 16 | UV exposure resistance                        | Keep in sunlight                       | Color and material remain stable             | Low      |
| 17 | Compatibility with cup holder (car)           | Place in vehicle cup holder            | Fits without tipping                         | Medium   |
| 18 | Stackability test (if stackable)              | Stack multiple cups                    | No slipping or getting stuck                 | Low      |
| 19 | Volume capacity validation                    | Measure with known volume              | Matches stated volume                        | Medium   |
| 20 | Long-term usage durability                    | Use daily for weeks                    | No cracks, stains, or breakage               | Medium   |

---

## 4. Facebook "Like" Button
**Introduction:** This test validates functionality, UI/UX, and behavior of the Facebook "Like" button in different scenarios across web and mobile.

| #  | Test Case Description                              | Steps to Execute                                   | Expected Result                               | Priority |
|----|----------------------------------------------------|----------------------------------------------------|-----------------------------------------------|----------|
| 1  | Verify Like button is visible                      | Open post or content                               | Like button is present                        | High     |
| 2  | Test single Like action                            | Click Like                                         | Button turns blue and Like count increases    | High     |
| 3  | Test Unlike action                                 | Click Liked again                                  | Like is removed, count decreases              | High     |
| 4  | Verify initial Like count                          | Open a post                                        | Count matches backend data                    | High     |
| 5  | UI feedback on hover                               | Hover over button (web)                            | Tooltip or animation appears                  | Low      |
| 6  | Like from mobile browser                           | Use mobile browser to like                         | Works consistently like app/web               | Medium   |
| 7  | Test Like across different posts                   | Like multiple posts                                | All reflect correct state                     | High     |
| 8  | Test Like on restricted/private content            | Try liking private post                            | Like option not available or shows warning    | Medium   |
| 9  | Verify Like reflects in activity log               | Like something, check profile                      | Action appears in user’s activity             | Medium   |
| 10 | Performance under load                             | Like multiple posts quickly                        | No lag or delay                               | Medium   |
| 11 | Responsive layout                                  | Resize browser window                              | Like button adjusts layout                    | Low      |
| 12 | Accessibility check (tab and screen reader)        | Navigate via keyboard/screen reader                | Button accessible with label                  | Medium   |
| 13 | Emoji reaction availability                        | Hold Like button                                   | Shows reaction menu                           | Medium   |
| 14 | Test Like with no network                          | Disable internet, press Like                       | Shows error or saves offline                  | High     |
| 15 | Verify server sync on Like                         | Like post, reload page                             | Like persists accurately                      | High     |
| 16 | Test rapid toggling                                | Like/unlike repeatedly                            | No crash or unexpected behavior               | Medium   |
| 17 | Analytics tracking for Like                        | Trigger Like                                       | Logged in analytics backend (if testable)     | Medium   |
| 18 | Permissions validation (blocked user)              | Block user and test Like                           | Like button not functional for blocked users  | Medium   |
| 19 | Verify consistency across feeds                    | Like in feed and on full post                      | Both reflect same state                       | High     |
| 20 | Browser compatibility                              | Like using various browsers                        | Button functions properly on all              | High     |

---

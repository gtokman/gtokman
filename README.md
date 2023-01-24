
<a href="https://twitter.com/f6ary">
  <img align="left" alt="Gary's | Twitter" width="22px" src="https://raw.githubusercontent.com/peterthehan/peterthehan/master/assets/twitter.svg" />
</a>
<a href="https://www.linkedin.com/in/garytokman/">
  <img align="left" alt="Gary's LinkedIN" width="22px" src="https://raw.githubusercontent.com/peterthehan/peterthehan/master/assets/linkedin.svg" />
</a>
</a>
<a href="https://www.patreon.com/6ary">
  <img align="left" alt="Gary's Medium" width="22px" src="https://user-images.githubusercontent.com/12258850/114738284-d2b6c700-9d15-11eb-8071-96fd30aa8b11.png" />
</a>
<a href="https://github.com/gtokman">
  <img align="left" alt="Gary's Counter" src="https://visitor-badge.glitch.me/badge?page_id=gtokman.gtokman" />
</a>

<br>
<br>

```swift

import Foundation

struct Profile: CustomStringConvertible {
    
    let name = "Gary Tokman"
    
    var description: String {
        """
        \(name)\n
        I am a software engineer and designer, currently
        working on trycandle.com. We are building finance
        tools with the goal of improving people's lives.\n
        """
    }
    
    enum Skill: String, CaseIterable {
        case figma, framer, finalCut
        case rN, TypeScript, JS
        case swift, objc, uIKit, swiftUI
    }
    
    func proficient(in skills: [Skill] = .allCases) -> String {
        skills
            .lazy
            .map(\.rawValue)
            .map(\.capitalized)
            .map { "- " + $0 + "\n" }
            .reduce("Skills: \n", +)
    }
}

// Paste into a playground!
let profile = Profile()
print(profile.description)
print(profile.proficient())

```

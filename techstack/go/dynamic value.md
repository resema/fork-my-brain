#go #interface 

Dynamic value is the actual value assigned. Interface type value is `nil` iff both [dynamic type](/techstack/go/dynamic%20type.md) and dynamic value are `nil`.
The effect is that even if interface type value holds a `nil` pointer then such interface is not `nil`
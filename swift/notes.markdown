## What's the difference?

```
extension Dictionary {
	init<S>(_ sequence: S) where S: Sequence, S.Iterator.Element == (key: Key, value: Value) {
		self = [:]
		self.merge(sequence)
	}
}
```

```
extension Dictionary {
	init<S: Sequence>(_ sequence: S) where S.Iterator.Element == (key: Key, value: Value) {
		self = [:]
		self.merge(sequence)
	}
}
```

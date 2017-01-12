## allMatch

检查一个序列中的所有元素是否全部都满足某个条件：
!sequence.contains { !condition }

其实可以用一个更具有描述性名字的新函数将它封装起来:    
```swift
extension Sequence {
	public func allMatch(predicate: (Iterator.Element) -> Bool) -> Bool {
    //对于一个条件，如果没有元素不满足它的话，那意味着所有元素都满足它：
		return !self.contains{ !predicate($0) }
	}
}
```

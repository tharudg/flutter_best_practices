# Flutter Development

Best practices to create UI/UX

## 

* Split Large Widgets into Smaller Widgets.
```dart
class NaveBar extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView(scrollDirection: Axis.horizontal,children: [
      NavBarItem(label: "Home",icon: Icons.home,onTap: (){print('home');}),
      NavBarItem(label: "Event",icon: Icons.event,onTap: (){print('event');}),
      NavBarItem(label: "Profile",icon: Icons.account_circle,onTap: (){print('profile');})
    ],);
  }
}

class NavBarItem extends StatelessWidget {
  final String label;
  final IconData icon;
  final VoidCallback onTap;

  const NavBarItem({Key key, this.label, this.icon, this.onTap}) : super(key: key);
  @override
  Widget build(BuildContext context) {
    return InkWell(,onTap: onTap, child: Column(children: [Text(label), Icon(icon)],));
  }
}

```

* Use Const Widgets

```dart
Container(
 child: Row(children: <Widget>[
 const Text(‘Use Const widgets’,),
 const Padding(
 padding: EdgeInsets.all(10),
 child: const Icon(Icons.date_range,)
 ),]),);
```
* Use Animations and Effects Sparingly
```bash
Some widgets that might lead to performance
issues include Opacity, Chip, ColorFilter, and ShaderMask.
For example to implement image fading, use
the FadeInImage widget instead of the Opacity widget.
For animations, you can use the AnimatedOpacity widget. 
 The problem encountered when using the Opacity 
widget for animations is that it causes the widget 
and it’s subtree to rebuild each frame.
 This can be quite costly, especially
when you have a large widget tree.
 
```
* Remove Unused Resources
* Use builders instead of for loops inside widgets
```
for loop inside your widget tree makes life difficult for
Flutter when rebuilding widgets and might affect your performance.

* Use ListView.builder ,GridView.builder likewise

```
* When setState() is called on a State, all descendent widgets will rebuild. Therefore, Split widget into small widgets so the setState() call rebuilds only the part of the subtree, whose UI actually needs to change.

* Check for boundary cases and handle layout overflows properly
```bash
* The widgets should take care of responsiveness of the application.
* Use of widgets which will handle screen overflows like Expanded to avoid 
overflow errors.
```

Make your React Native apps more accessible with these tools

Your React Native apps should work for everyone.

Seems obvious, right? But not everyone has perfect vision, or good hand-eye coordination, or a fast internet connection. Just in the US alone, [about 13% of adult Americans “have trouble” seeing](https://www.afb.org/research-and-initiatives/statistics). Inaccessible applications can reduce user engagement, hurt your brand image, and even have legal implications. Making sure apps are inclusive and accessible for everyone is good for business and just good, morally!

This article will give a few examples of steps you can take to make your apps more accessible.

## Accessibility properties

Both Android and iOS have built-in assistive functionality, like TalkBack or VoiceOver. These tools, also known as accessibility readers, read an app’s contents out loud to users. Essentially, they are a supportive interface next to the visual design of the app. We can help these readers understand what they need to talk out loud by using [the accessibility properties in React Native](https://reactnative.dev/docs/accessibility).

When using an icon as a button, readers might have trouble communicating the kind of action it performs. Without a textual description, there is no way to “read it out loud”.

```
<TouchableOpacity onPress={deleteItem}>  <TrashIcon /></TouchableOpacity>
```

In React Native, we can add a textual description without actually displaying the text. This text helps accessibility readers communicate the action that will be performed when pressing the button. We can do that by defining the accessibility properties.

```
<TouchableOpacity  onPress={deleteItem}  accessible={true}  accessibilityLabel="Press to delete"  accessibilityHint="The item will be deleted permanently">  <TrashIcon /></TouchableOpacity>
```

In this example, we added three different properties.

1.  `accessible` -This property tells React Native to group the content into a single selectable component. When users tap the button, Android and iOS will select everything from the touchable opacity.
2.  `accessibilityLabel` - This describes how users can use the button. Accessibility readers will tell the user to “Press to delete”.
3.  `accessibilityHint` - This optional description tells users what will happen after pressing the button.

These properties enable accessibility readers to describe the action when pressing the button. Without the text displayed, it will read out “Press to delete, the item will be deleted permanently” when accessibility users are trying to understand the button.

For a live example, check out [this demo of an accessible delete icon](https://snack.expo.io/@bycedric/accessibility-example-button).

## Design

Another important aspect of accessibility is the design of your app. When using different backgrounds and text colors, it’s good to keep contrast in mind. This contrast can be important for people who need glasses, for example.

![Blurry white text over a light background](https://static-assets.codecademy.com/Courses/Learn-React-Native/2-core-components/bad-example.png)

In the image above, we add text over a background image with low contrast. Some of the white text fades into the background. With blurry vision, this text becomes close to unreadable.

![Blurry white text over a dark background](https://static-assets.codecademy.com/Courses/Learn-React-Native/2-core-components/good-example.png)

In this image, we added more contrast by using a dark color overlay on the background image. It increases the contrast with the white text, preventing it from fading into the background image. For people with blurry vision, this increases their user experience while having a minimal impact on the design.

## Continue reading

Accessibility doesn’t stop at adding labels or improving design. Other aspects might also be relevant for an app, like mobile internet costs in different parts of the world. Google has excellent resources on more accessibility factors. You can [find these resources at “Building for billions”](https://developers.google.com/billions).

If you aren’t sure where to start, watch this video on how you could apply some of these accessibility techniques in React Native. It walks you through an unoptimized onboarding screen and shows how you can improve it.

https://www.youtube.com/watch?v=S3DzcCrEGbc
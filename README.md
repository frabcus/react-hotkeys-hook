# react-hotkeys-hook
React hook for using keyboard shortcuts in components.
This is a hook version for the [hotkeys-js] package.

### Installation

`npm install react-hotkeys-hook`

or

`yarn add react-hotkeys-hook`

Make sure that you have `react@next` and `react-dom@next` installed, or otherwise hooks won't work for you.

### Usage
With TypeScript
```
export const ExampleComponent: React.FunctionComponent<{}> = () => {
  const [count, setCount] = useState(0);
  useHotKeys('ctrl+k', () => setCount(count + 1));

  return (
    <p>
      Pressed {count} times.
    </p>
  );
};
```

Or plain JS:
```
export const ExampleComponent = () => {
  const [count, setCount] = useState(0);
  useHotKeys('ctrl+k', () => setCount(count + 1));
    
  return (
    <p>
      Pressed {count} times.
    </p>
  );
};
```

The hook takes care of all the binding and unbinding for you.
As soon as the component mounts into the DOM, the key stroke will be
listened to. When the component unmounts it will stop listening.

### Call Signature

`useHotkey(key: string, (keys: string, callback: (event: KeyboardEvent, handler: HotkeysEvent) => void))`

The callback function takes the exact parameters as the callback function in the hotkeys-js package.
See [hotkeys-js] documentation for more info or look into the typings file.

### Found an issue or have a feature request?

Open up an issue or pull request and participate.

### Authors

* Johannes Klauss

---

MIT License.

---

[hotkeys-js]: https://github.com/jaywcjlove/hotkeyshotkeys-js
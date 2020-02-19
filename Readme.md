# TgMDE - Telegram Markdown Editor

Simple WYSIWYG Markdown editor with only support for [Telegram flawored text](https://core.telegram.org/bots/api#markdown-style). 

All rules that is supported:

    *bold text*
    _italic text_
    [inline URL](http://www.example.com/)
    [inline mention of a user](tg://user?id=123456789)
    `inline fixed-width code`
    ```block_language
    pre-formatted fixed-width code block
    ```

Project is based on the beautiful [SimpleMDE Markdown Editor](https://simplemde.com/).

## React component from TgMDE

**TgMdEditor.jsx**

```jsx
import React, { useEffect } from 'react'
import * as TGMDE from 'tgmde/dist/tgmde.min.js'
import 'tgmde/dist/tgmde.min.css'


const TgMdEditor = ({ value, setValue }) => {

  useEffect(() => {
    const tgmde = new TGMDE({});
    tgmde.value(value);
    tgmde.codemirror.on('change', () => setValue(tgmde.value()))
  }, [])
  
  
  return (
    <div className="tgmde">
      <textarea />
    </div>
  )
}

export default TgMdEditor

```

your **Form.jsx**

```jsx
// ...

import TgMdEditor from './path/to/TgMdEditor';

// ...

   <TgMdEditor value={ state.text }  setValue={ setText } />

// ...

```

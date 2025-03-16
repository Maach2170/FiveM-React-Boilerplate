
# Basic Nui React JS Script Boilerplate

Boilerplate To Use ReactJS With Your FiveM Server!
*ReactJS & Vite & SASS*


## Prerequisites
* [NodeJS | v11+](https://nodejs.org/en/)



## How To Install And Use

```bash
    cd web
    npm install
    npm run dev
```

When you make changes be sure to view the changes in game
```bash
    npm run build
```

## If You Want To Use ScSS (SASS)

```bash
    cd web
    npm install sass-embedded
```

## Development

Refer To `main.jsx 7` to find the useState to view the changes on your web
 - *Remember To Change It Before You Build*

 Change This:

```lua
  const [visible, setVisible] = useState(false) // Reducer

  const handleNuiCallback = (event) => {
    switch (event.data.action) {
      case 'open':
        setVisible(true)
        break
    }
  }

  const keyHandler = (e) => {
    if ('Escape'.includes(e.code) && visible) {
      setVisible(false)
      fetch(`https://${GetParentResourceName()}/hide`, {
        method: 'post'
      })
    }
  }

  useEffect(() => {
    if (visible) {
      document.body.style.display = 'flex'
    } else {
      document.body.style.display = 'none'
    }
  }, [visible])

  window.addEventListener('message', handleNuiCallback)
  window.addEventListener('keydown', keyHandler)
  ```

# classic-wap-game-layout
First, the layout uses Two CSS Grids. 
* The first Grid **<body>** makes sure that `<aside>` tags surrounding `<section>` make it centered.
  ```
  	display: grid;
		grid-auto-flow: column;
  ```
* The second Grid **<section>** is a container for the `<header>, <main> and <footer>`
  
### Setting Empty HTML element's height to line height by giving it a fake zero lenght space symbol
#### Empty HTML elements having no height will contain pseudo-element `before` containing \200B` (zero length space)
* **Solved:** The Invisible `Grid Item` without Text would be shown with `height` too low to see the `Grid Item`
There was a problem that if the `Grid Item` beloning to `Grid Container` was completely empty - not containing any text, its `height` would become too low to see it.
* **Solution:** Every HTML element that is empty will have pseudo-element `before` that will contain `\200B` (zero length space) which won't be seen nor interactive by HTML processors.
  ```
  <style>
  *:empty:before { 
		content:'\200B';
	}
  ...
  ```
  
  
![](./Screenshot_from_2019-07-24_23-03-07.png)

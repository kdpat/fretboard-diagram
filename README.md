Draws an svg diagram of an instrument's fretboard. Users can change the number of strings and frets and provide a callback for when a fret is clicked.

![screenshot](fretboard-diagram-screenshot.png)

# Example Usage

```
<script type="text/javascript">
  /**
   * ZPiDER's answer from https://stackoverflow.com/questions/1484506/random-color-generator
   */
  const randomColor = () => '#' + ((1 << 24) * Math.random() | 0).toString(16);

  const dots = [
    {string: 5, fret: 3, color: randomColor()},
    {string: 3, fret: 2, color: randomColor()},
    {string: 1, fret: 0, color: randomColor()},
  ];

  const opts = {
    dots,
    showFretNums: true,
    label: 'Amin',
    onClick: coord => console.log(`clicked on string: ${coord.string}, fret: ${coord.fret}`)
  };

  const diagram = makeFretboardDiagram(opts);
  console.log(diagram);

  const div = document.getElementById('Am-diagram');
  div.appendChild(diagram);
</script>
```

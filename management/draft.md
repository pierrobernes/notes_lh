
```mermaid
gitGraph:
options
{
    "nodeSpacing": 100,
    "nodeStrokeColor": "red",
    "nodeRadius": 10,
    "lineStrokeWidth": 5,
    "branchOffset": 100,
    "lineColor": "grey",
    "leftMargin": 50,
    "branchColors": ["#442f74", "#983351", "#609732", "#AA9A39"],
    "nodeLabel": {
        "width": 125,
        "height": 100,
        "x": -25,
        "y": 10
    }
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```


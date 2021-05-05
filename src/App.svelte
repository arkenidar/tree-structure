<script>
import Tree from "./Tree.svelte"
let test_tree1=[1,2,3,[4,5]]
let test_tree2=[
    [
        "out1",
        "fibonacci algorithm"
    ],
    [
        "set",
        "x",
        0
    ],
    [
        "set",
        "y",
        1
    ],
    [
        "loop",
        [
            "expr",
            [
                "get",
                "x"
            ],
            "<",
            256
        ],
        [
            [
                "out1",
                [
                    "get",
                    "x"
                ]
            ],
            [
                "set",
                "z",
                [
                    "expr",
                    [
                        "get",
                        "x"
                    ],
                    "+",
                    [
                        "get",
                        "y"
                    ]
                ]
            ],
            [
                "set",
                "x",
                [
                    "get",
                    "y"
                ]
            ],
            [
                "set",
                "y",
                [
                    "get",
                    "z"
                ]
            ]
        ]
    ]
]
let tree=test_tree2
</script>

<Tree {tree}/>
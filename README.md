# The p-cut model
This repository present the workflow for the cutting probability model (p-cut model).

## Folder structure
The folder is organized as follows:

```bash
├── README.md
├── resources
│   └── inhouse
│   └── public
├── results
│   └── input
│   └── intermediary
│   └── output
│   └── plots
└── workflow
    ├── Snakefile
    ├── envs
    ├── rules
    ├── sandbox
    └── scripts
```


README.md provides information on the repository structuration and explains the data analysis workflow.
 
The workflow code goes into a subfolder `workflow`, while the configuration is stored in a subfolder `config`. Inside of the workflow subfolder, the central `Snakefile` marks the entrypoint of the workflow (it will be automatically discovered when running snakemake from the root of above structure). In addition to the central `Snakefile`, rules are stored in a modular way, using the subfolder `workflow/rules`. Such modules should end with `.smk`, the recommended file extension of Snakemake. Further, scripts are stored in a subfolder `workflow/scripts`. Conda environments are stored in the subfolder `workflow/envs` (they are kept as finegrained as possible to improve transparency and maintainability).

All output files generated in the workflow are stored under `results`, unless they are rather retrieved `resources`, in which case they should be stored under resources. The latter subfolder also contains small resources that are delivered along with the workflow via Git. The folder `resources` is further divided into two subfolders: `inhouse` which stores homemade and private data, and `public` which stores public data retrieved from public databases. The `resources` folder should contain processing files separated into an `input` subfolder (input data, e.g., filtered data from `resources` folder, or slightly arranged data), an `intermediary` subfolder (intermediate processing data), and an `output` subfolder (output data, that directly produces plots, maps, and figures, for instance).

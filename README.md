# ComboTree jQuery Plugin

ComboTree is a jQuery Plugin which is a combobox item with tree structured data list and multi/single selection options and more. It has been developed to manage large amount of choices and multi selection property. 

## Features:
- Tree structured data list in combobox dropdown menu
- Multi/Single selection optional
- It returns selection(s) data as Title/Id array
- Filtering
- JSON Data source
- Key Controls
 
## Dependencies:
- jQuery
- icontains.js (filtering. It can be found in repository)
 
## Configurations:
- isMultiple: {True/False} | Whether it is multiple selection behaviour or single.
- source: {JSON Data Array} | Takes source of combobox dropdown menu as a JSON array (see Sample).
- expandAll: {True/False} | Whether to expand the tree or not.
- parentIncludesChilds: {True/False} | Whether selecting a parent implicitely means childs are selected as well and thus cannot be selected independently (only for multi select).

## Usage

There should be an input element to apply and a JSON Data source.

	comboTree1 = $('#justAnInputBox').comboTree({
		source : SampleJSONData,
		isMultiple: true,
		expandAll: false,
		parentIncludesChilds: true
	});

	// Array, One title/id, or False value return
	var selectedTitles = comboTree1.getSelectedItemsTitle();
	var selectedIds = comboTree1.getSelectedItemsId();
	
	// copy the selected IDs into a hidden input element on submit
	$('form').submit(function(event) {
		$('<input>').attr({ type:'hidden', name: 'justAnInputBox_ids'}).val(comboTree1.getSelectedItemsId()).appendTo('form');
	});
	
	// To remove plugin
	comboTree1.destroy();
	


## Sample JSON DATA

Three parameter are needed: id, title and subs.

	var SampleJSONData = [
	{
	    id: 0,
	    title: 'choice 1  '
	}, {
	    id: 1,
	    title: 'choice 2',
	    preselect: true,
	    subs: [
	        {
	            id: 10,
	            title: 'choice 2 1'
	        }, {
	            id: 11,
	            title: 'choice 2 2'
	        }, {
	            id: 12,
	            title: 'choice 2 3'
	        }
	    ]
	}, {
	    id: 2,
	    title: 'choice 3'
	}, {
	    id: 3,
	    title: 'choice 4'
	}, {
	    id: 4,
	    title: 'choice 5'
	}, {
	    id: 5,
	    title: 'choice 6',
	    subs: [
	        {
	            id: 50,
	            title: 'choice 6 1'
	        }, {
	            id: 51,
	            title: 'choice 6 2',
	            subs: [
	                {
	                    id: 510,
	                    title: 'choice 6 2 1'
	                }, {
	                    id: 511,
	                    title: 'choice 6 2 2'
	                }, {
	                    id: 512,
	                    title: 'choice 6 2 3'
	                }
	            ]
	        }
	    ]
	}, {
	    id: 6,
	    title: 'choice 7'
	}
	];


## User Friendly

Key controls, well designed and esasy-read code structure, definitions and clear variable names are choosen to be read and used as much as comfortable I could.

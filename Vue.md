A. Accessing Child Component (Instance & Elements):

	1. Directly access a child component using ref:
		<base-input ref="usernameInput"></base-input> // base-input is a child component used in parent
		this.$refs.usernameInput.focus() //focus() is a method defined in child component

		Link: https://github.com/kabircse/LearnVue/blob/main/Examples/AccessChildComponentUsingRef.md

	2. Using event bus:
		<ChildForm :item="item" :bus="bus" ref="form" />
		this.bus.$emit('submit')

		https://github.com/kabircse/LearnVue/blob/main/Examples/AccessChildComponentUsingEventBus.md

	
	
B. Accessing Parent component(Instance & Elements) from child:

	1. In child component use this.$emit('eventName'):
	methods:{
	    openMenu(){
		this.$emit('openMenu')
	    }
	}

	and in parent component use @eventName attribute:

	<child @openMenu="main_menu=true"></child> // or call your method

	
	2. useing vue event system
	Vue's event system is simple. In child use a dispatch :

	this.$dispatch('child-coucou', this);

	And listen in parent :

	this.$on('child-coucou', function (child) {
	  // Make something there with child reference
	})

	3.
	this.$parent.$options.methods.someParentMethod(data)
	this.$parent.someParentMethod(data) // How do I call a parent method?

	In the component ...

	methods: {
	    something() { this.$emit('event', [x: y]);
	}

	In the parent template ...

	<component @event="handler"></component>

	In the parent script ...

	methods: {
	    handler(params) {
		console.log(params);
	    }
	}
	

	Accessing Child Component (Instance & Child Elements):
	1. Directly access a child component using ref:
		<base-input ref="usernameInput"></base-input> // base-input is a child component used in parent
		this.$refs.usernameInput.focus() //focus() is a method defined in child component

		Link: https://github.com/kabircse/LearnVue/blob/main/Examples/AccessChildComponentUsingRef.md

	2. Using event bus:
		<ChildForm :item="item" :bus="bus" ref="form" />
		this.bus.$emit('submit')

		https://github.com/kabircse/LearnVue/blob/main/Examples/AccessChildComponentUsingEventBus.md

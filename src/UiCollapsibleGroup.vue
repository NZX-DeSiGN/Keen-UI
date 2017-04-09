<template>
    <div class="ui-collapsible-group">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'ui-collapsible-group',

    methods: {
        opened(collapsible) {
            for (var child of this.$children) {
                if (child === collapsible || child.$options._componentTag !== 'ui-collapsible') continue;
                child.toggleCollapsible(false);
            }
        }
    }
};
</script>
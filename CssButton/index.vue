<template>
    <button class="dafault-button"
            :class="['css-btn-'+size, 'btn-type-'+type, getDisabledClass(), getHoverClass()]"
            :disabled="disabled">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'cssButton',
    props:{
        border: {
            type: Boolean,
            default: false
        },
        hover: {
            type: Boolean,
            default: true
        },
        type: {
            type: String,
            default: 'default'
        },
        size: {
            type: String,
            default: 'medium'
        },
        disabled: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        getHoverClass() {
            if (this.hover && !this.disabled) {
                return 'hover-btn'
            } else {
                return ''
            }
        },
        getDisabledClass() {
            if (this.disabled) {
                return 'disabled-btn'
            } else {
                return ''
            }
        }
    }
}
</script>

<style>
.dafault-button {
    padding: 12px 22px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 14px;
    cursor: pointer;
    border-radius: 6px;
    border: 1px solid #999;
}
/* 点击后取消默认样式 尚未完成 */
/* .dafault-button::after {
    border: none;
} */
.hover-btn:hover {
    opacity: 0.8;
}
.btn-type-success {
    background-color: #4CAF50;
    color: white;
    border: none;
}
.btn-type-danger {
    background-color: #f83a54ef;
    color: white;
    border: none;
}
.btn-type-warning {
    background-color: #e6c65fef;
    color: white;
    border: none;
}
.btn-type-primary {
    background-color: #519df5ef;
    color: white;
    border: none;
}
.btn-type-default {
    background-color: #fff;
}
.css-btn-medium {
    font-size: 14px;
}
.css-btn-large {
    font-size: 18px;
}
.css-btn-small {
    font-size: 12px;
}
.disabled-btn {
    cursor: default;
    opacity: 0.5;
}
</style>
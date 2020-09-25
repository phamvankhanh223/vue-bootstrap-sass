<template>
  <div style="margin-bottom:40px">
    <b-form-group label="Using options array:">
      <b-form-checkbox-group
        id="checkbox-group-1"
        v-model="selected"
        :options="options"
        name="flavour-1"
      ></b-form-checkbox-group>
    </b-form-group>

    <b-form-group label="Using sub-components:">
      <b-form-checkbox-group id="checkbox-group-2" v-model="selected" name="flavour-2">
        <b-form-checkbox value="orange">Orange</b-form-checkbox>
        <b-form-checkbox value="apple">Apple</b-form-checkbox>
        <b-form-checkbox value="pineapple">Pineapple</b-form-checkbox>
        <b-form-checkbox value="grape">Grape</b-form-checkbox>
      </b-form-checkbox-group>
    </b-form-group>

    <div>Selected: <strong>{{ selected }}</strong></div>

    <select name="select-tag" id="select-tag1" v-model="selected" multiple>
      <option v-for="(option, index) in options" :key="index" :value="option.value">{{ option.text }}</option>
    </select>

    <div class="default-checkbox">
      <div class="one-checkbox" v-for="(option,index) in options" :key="index">
        <input type="checkbox" :value="option.value" v-model="selected">
        <label for="index">{{ option.text }}</label>
      </div>
    </div>

    <input
      type="checkbox"
      v-model="toggle"
      true-value="yes"
      false-value="no"
    >
    <label for="">get true false: {{ toggle }}</label>

    <input type="text" v-model.trim="age">
    {{ age }}
  </div>
</template>

<script>
export default {
  data () {
    return {
      selected: [], // Must be an array reference!
      options: [
        { text: 'Orange', value: 'orange' },
        { text: 'Apple', value: 'apple' },
        { text: 'Pineapple', value: 'pineapple' },
        { text: 'Grape', value: 'grape' }
      ],
      toggle: 'yes',
      age: '   khanh pham pham mmm        '
    }
  }
}
</script>

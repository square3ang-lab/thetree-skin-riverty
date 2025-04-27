<template>
    <setting>
        <setting-item-select label="사이드바 설정" ckey="riverty.sidebar" :default="sidebar">
            <option value="default">기본</option>
            <option value="fix">고정</option>
            <option value="hide">숨김</option>
        </setting-item-select>
        <setting-item-checkbox label="내비게이션 바 고정" ckey="riverty.fixed_navbar" />
        <setting-item-checkbox label="페이지 이동 시 검색 창 초기화" ckey="riverty.reset_search_on_move" :default="true" />
        <template v-if="$store.state.session.quick_block">
            <hr />
            <setting-item-checkbox label="[ADMIN] 관리 편의성 개선" ckey="riverty.admin_convenience" :default="true" />
        </template>
    </setting>
</template>

<script>
import Common from '~/mixins/common';

import Setting from '~/components/setting';
import SettingItemCheckbox from '~/components/settingItemCheckbox';
import SettingItemSelect from '~/components/settingItemSelect';

export default {
    mixins: [Common],
    components: {
        Setting,
        SettingItemCheckbox,
        SettingItemSelect,
    },
    computed: {
        sidebar() {
            return "default";
        }
    }
}
</script>
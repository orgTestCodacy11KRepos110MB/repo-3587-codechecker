<template>
  <div>
    <v-avatar
      left
      :size="32"
    >
      <detection-status-icon
        :status="item.detectionStatus"
        :size="16"
      />
      <review-status-icon
        :status="item.reviewStatus"
        :size="16"
      />
    </v-avatar>
    {{ item.runName }}:{{ item.fileName }}:L{{ item.line }}
    <v-chip
      :color="getBugPathLenColor(item.bugPathLength)"
      label
      light
      small
    >
      {{ item.bugPathLength }}
    </v-chip>
  </div>
</template>

<script>
import { DetectionStatusIcon, ReviewStatusIcon } from "@/components/Icons";
import { BugPathLengthColorMixin } from "@/mixins";

export default {
  name: "SelectSameReportItem",
  components: {
    DetectionStatusIcon,
    ReviewStatusIcon
  },
  mixins: [ BugPathLengthColorMixin ],
  props: {
    item: { type: Object, required: true }
  }
};
</script>

<template>
  <v-runtime-template :template="html" />
</template>

<script>
import VRuntimeTemplate from "v-runtime-template";
import Asset from "./Asset";

export default {
  components: {
    VRuntimeTemplate,
    Asset
  },
  props: {
    html: {
      type: String,
      required: true,
    },
  },
  methods: {
    getNode: function (codename, id) {
      const query = this.$static[codename];

      if (typeof query === "undefined") {
        return null;
      }

      const edges = query.edges.filter((edge) => edge.node.id === id);

      if (edges.length === 1) {
        return edges[0].node;
      }

      return null;
    },
  },
};
</script>

<static-query>
query RichText {
  asset: allAsset {
    edges {
      node {
        id,
        url(width: 1200, format: "webp"),
        placeholderUrl: url(width: 50, format: "webp")
        description
      }
    }
  }
}
</static-query>
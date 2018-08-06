<template>
   <view class="container">
    <apollo-provider :client="client">
      <query :query="cquery">
        <view render-prop-fn="children">
          <text v-if="args.loading">Loading...</text>
          <text v-else-if="args.error">An error occured</text>
          <view v-if="args.data && args.data.lookup">
            <text v-for="album in args.data.lookup.artist.releaseGroups.edges">
              {{album.node.title}}
            </text>
          </view>
        </view>
      </query>
    </apollo-provider>
   </view>
</template>

<script>
import { ApolloClient } from 'apollo-client';
import { HttpLink } from 'apollo-link-http';
import { InMemoryCache } from 'apollo-cache-inmemory'
import { ApolloProvider, Query } from 'react-apollo';

const client = new ApolloClient({
  link: new HttpLink({ uri: 'https://graphbrainz.herokuapp.com/' }),
  cache: new InMemoryCache()
});

import { GET_NAMES } from "./queries.js";
export default {
  data: {
    test: false,
    dataSource: 0,
    client: client,
    cquery: GET_NAMES
  },
  components: { ApolloProvider, Query }
};
</script>

 
<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>

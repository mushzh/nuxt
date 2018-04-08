<template>
    <section class="recipes">
        <Airbnb
            v-for="airbnb in airbnbs"
            :key="airbnb.id"
            :thumbnail="airbnb.thumbnail"
            :title="airbnb.title"
            :id="airbnb.id"
            :previewText="airbnb.previewText"
        />
    </section>
</template>

<script>
import Airbnb from '@/components/Airbnb'

export default {
    components: {
        Airbnb
    },
    asyncData() {
        return new Promise((resolve, reject) =>{
            setTimeout(() => {
                resolve({
                    airbnbs: [
                        {
                            id: "1",
                            title: "Private island in sunny Hvaler",
                            previewText: "Small cottage on a 10.000 sq.m private island in the adventurous archipelago of Hvaler.",
                            thumbnail: "https://a0.muscache.com/im/pictures/33086851/4a82f1ad_original.jpg?aki_policy=xx_large"
                        },
                        {
                            id: "2",
                            title: "Holiday in Toscany in the Strettoio",
                            previewText: "ご自宅で過ごすように、素晴らしい滞在であることを願っています!",
                            thumbnail: "https://a0.muscache.com/im/pictures/10431290/aa5f0e00_original.jpg?aki_policy=xx_large"
                        }
                    ]
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
.recipes{
    display: flex;
    flex-flow: row warp;
    justify-content: center;
    align-items: center;
}

</style>

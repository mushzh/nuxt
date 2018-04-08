<template>
    <section class="single-airbnb">
        <h1>Room No.{{ $route.params.id }} {{airbnb.title}}</h1>
        <div>
            <img class="airbnb-image" :src="airbnb.thumbnail" :alt="airbnb.title">
        </div>
        <p class="p-airbnb"><b>{{ airbnb.descriptionText1 }}</b></p>
        <p class="p-airbnb">{{ airbnb.descriptionText2 }}</p>
        <br>
        <p class="p-airbnb"><b>{{ airbnb.descriptionText3 }}</b></p>
        <p class="p-airbnb">{{ airbnb.descriptionText4 }}</p>
        <br>
        <p class="p-airbnb"><b>{{ airbnb.descriptionText5 }}</b></p>
        <p class="p-airbnb">{{ airbnb.descriptionText6 }}</p>
        <br>
    </section>
</template>

<script>
export default {
    asyncData(context) {
        return new Promise((resolve, reject) =>{
            setTimeout(() => {
                resolve({
                    airbnb: [
                        {
                            id: "1",
                            title: "Private island in sunny Hvaler",
                            previewText: "Small cottage on a 10.000 sq.m private island in the adventurous archipelago of Hvaler.",
                            descriptionText1: "概要",
                            descriptionText2: "Small cottage on a 10.000 sq.m private island in the adventurous archipelago of Hvaler. Accomodates one family (2+3) or four adults. (2+2).Boat with motor available.",
                            descriptionText3: "スペース",
                            descriptionText4: "Private island in the beautiful archipelago of Hvaler; the municipality with the highest number of sunny days per year in Norway!",
                            descriptionText5: "キャンセル",
                            descriptionText6: "チェックイン7日前までに解約すれば、サービス料を除き50%が返金されます。その後の解約では、宿泊料金は返金不可となります。サービス料は、予約後48時間以内かつチェックイン前の解約に限り返金されます。",
                            thumbnail: "https://a0.muscache.com/im/pictures/33086851/4a82f1ad_original.jpg?aki_policy=xx_large"
                        },
                        {
                            id: "2",
                            title: "Holiday in Toscany in the Strettoio",
                            previewText: "ご自宅で過ごすように、素晴らしい滞在であることを願っています!",
                            descriptionText1: "概要",
                            descriptionText2: "ご自宅で過ごすように、素晴らしい滞在であることを願っています!",
                            descriptionText3: "スペース",
                            descriptionText4: "My apartment is very unique and well finished in the Tuscan tradition. He has his privacy in all, well tenuto.C 'kitchen is a living room of about 14sqm with small sofa bed for one and a half, provided fgrigorifero, electric oven, sink, stove, washing machine and all the accessories to be able to safely eat , then there is a well-kept brick bathroom with shower and sink, bathroom, we also have the sleeping area consists of a small room with a French bed, hallway with wardrobe, etc. ....",
                            descriptionText5: "キャンセル",
                            descriptionText6: "宿泊7日前までに解約すれば、全額返金されます。それを過ぎてからの解約では、宿泊料金の50%とサービス料全額が返金されます。",
                            thumbnail: "https://a0.muscache.com/im/pictures/10431290/aa5f0e00_original.jpg?aki_policy=xx_large"
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
.single-airbnb {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
    padding: 30px;
}

.airbnb-image {
    width:100%
}

</style>

<template>
    <div class="container">
        <h3>User Edit Component</h3>
        <hr />
        <p>Ad : {{ $route.query.name }}</p>
        <p>Soyad : {{ $route.query.lastName }}</p>
        <button class="btn btn-primary" @click="saved = true">onayla</button>
        <div style="height: 800px;"></div>
        <p id="data">Burada baız bilgiler olabilir</p>
    </div>
</template>
<script>
export default {
    data() {
        return {
            saved: false,
        };
    },
    beforeRouteLeave(to, from, next) {
        if (this.saved) {
            next();
        } else {
            if (confirm("Tüm bilgileriniz kaybolabilir. Emin misiniz?")) next();
            else next(false);
        }
    },
};
</script>

<template lang="pug">
    .content
        //- h1.tm-title.tm-lh-title.tm-rf6.tm-bold Developer Portal
        a(href="/academy/0-welcome")
            card.mt-9(imageUrl="/graphics-sdk-course.png")
                .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted begin your cosmos journey
                h2.mt-1 Developer Portal
                //- .info-label.tm-lh-title.tm-rf-1.tm-muted ~126 Hours

                .content__intro__desc.tm-measure-narrow.tm-lh-copy.tm-muted Cosmos is a network of interoperable blockchains built on BFT consensus. <br/><br/> The ever-expanding ecosystem provides an SDK, tokens, wallets, applications, and services. Discover the Cosmos SDK to develop application-specific blockchains. <br/><br/> Ready to begin your journey?
                a(href="/academy/0-welcome").tm-button.mt-7.mb-5.tm-button-disclosure
                    span Start course

        .home__content__overview(v-if="$frontmatter.overview" id="overview")
            h2.home__content__overview__title {{$frontmatter.overview.title}}
            .home__content__overview__content(v-if="$frontmatter.overview.items")
                tm-faq.home__content__overview__content__item(v-for="item in $frontmatter.overview.items" :title="item.title" :description="item.description")

        .home__content__intro(v-if="$frontmatter.intro" v-for="intro in $frontmatter.intro").mb-8
            .home__content__intro__content(:class="intro.image ? 'home__content__intro__content__small' : ''")
                .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted(v-if="intro.overline") {{intro.overline}}
                h2.home__content__intro__content__title {{intro.title}}
                .home__content__intro__content__desc(v-html="intro.description" :class="intro.image ? 'tm-measure-narrower' : ''")
                a.tm-button.tm-button-disclosure.mt-7(v-if="intro.action" :href="intro.action.url")
                    span {{intro.action.label}}
            .home__content__intro__image(v-if="intro.image")
                tm-image(:src="intro.image")

        .tags
            .tags__description You aren't sure where to start? Take a look at all there is to dive in! <br/><br/> Start with the first chapter, or select one or more tags.
            .tags__list.mt-8
                .tags__wrapper(v-for="(tag, key) in $themeConfig.tags")
                    .tags__list__item(v-bind:style="{'background': tag.color || ''}" @click="updateFilterTags(key)" :class="{'tags__list__item__selected': isTagSelected(key)}") {{tag.label || ''}}


        .modules-intro__wrapper.mt-10.mb-10
            h3 Introduction to Cosmos
            .cards(v-if="$frontmatter.modulesIntroduction")
                .cards__wrapper(v-for="card in $frontmatter.modulesIntroduction")
                    card-links.cards__item(
                        :image="card.image" 
                        :title="card.title" 
                        :description="card.description" 
                        :tag="card.tag || null"
                        :links="card.links")

        .tutorials__wrapper
            h3 Tutorials
            .tutorials__description.mt-6 Getting started
            .cards(v-if="$frontmatter.tutorials")
                .cards__wrapper(v-for="card in $frontmatter.tutorials")
                    card-links.cards__item(
                        :image="card.image" 
                        :title="card.title" 
                        :description="card.description" 
                        :tag="card.tag || null"
                        :links="card.links")

        .exercises__wrapper
            h3 Hands-on exercise
            .exercises__description.mt-6 From zero to hero <br/> Work with the full Cosmo stack while developing a checkers game blockchain
            .cards(v-if="$frontmatter.exercises")
                .cards__wrapper(v-for="card in $frontmatter.exercises")
                    card-links.cards__item(
                        :image="card.image" 
                        :title="card.title" 
                        :description="card.description" 
                        :tag="card.tag || null"
                        :links="card.links")

        //- .tutorials__wrapper.mt-10
        //-     h3.tm-title.tm-lh-title.tm-rf3.tm-bold Tutorials
        //-     .tutorials
        //-         a.tutorials__item__small(href="/tutorials/understanding-authz/")
        //-             card
        //-                 .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted intermediate
        //-                 h4.mt-7 Understanding the Authz Module
        //-                 .mt-7.tm-lh-copy.tm-muted In this tutorial, you learn what the Authz module does, how to create and revoke authorizations, and how to execute authorized transactions on a local testnet.
        //-                 .mt-7.info-label.tm-rf-1.tm-muted 20 minute read
        //-         a.tutorials__item__large(v-bind:style="{'background-image': `url(/tutorial-bg-image.png)`}" href="https://docs.ignite.com/" target="_blank")
        //-             .tm-measure
        //-                 .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted Ignite CLI
        //-                 h2.mt-5 Build a chain in minutes


        //- .articles__wrapper.mt-10(v-if="$frontmatter.articles")
        //-     .articles__wrapper__title
        //-         h3.tm-title.tm-lh-title.tm-rf3.tm-bold Articles
        //-         //- div
        //-         //-     a(href="/").tm-link.tm-lh-solid.tm-rf1.tm-medium.tm-link-external
        //-         //-         span More articles
        //-     .articles.mt-8
        //-         .articles__item(v-for="article in $frontmatter.articles")
        //-             a.articles__item__container(:href="article.url" target="_blank")
        //-                 .articles__item__image(v-bind:style="{'background-image': `url(${article.image})`}")
        //-                 .articles__item__content
        //-                     .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted.articles__item__content__date {{article.date}}
        //-                     h4.articles__item__content__title.mx-5 {{article.title}}
        //-                     .info-label.articles__item__content__time.tm-rf-1.tm-muted.tm-lh-title {{article.time}} minute read

        .tools__wrapper.mt-10
            h3.tm-title.tm-lh-title.tm-rf3.tm-bold Tools
            .tools.mt-8
                .tools__item(v-for="tool in $frontmatter.tools")
                    .tools__item__container
                        .tools__item__icon
                            img(:src="tool.image" :alt="tool.title")
                        .tools__item__content
                            h5 {{tool.title}}
                            .mt-3 {{tool.description}}
                            .mt-6.tools__item__content__links
                                a(v-for="link in tool.links" :href="link.url" target="_blank").tm-link.tm-lh-solid.tm-medium.tm-link-external
                                    span {{link.name}}

        //- .support__wrapper.mt-10
        //-     card(imageUrl="/support-image.png" :bigCard="true").support__card
        //-         .tm-overline.tm-rf-1.tm-lh-title.tm-medium.tm-muted custom support
        //-         h2.content__support__title.mt-6 Need help bringing your project to life?
        //-         .mt-5.tm-lh-copy.tm-muted.tm-measure-narrow Apply for support and get help with funding applications, grants, technology, architecture, and getting in touch with the ecosystem.
        //-         .mt-8
        //-             a.tm-button.tm-button-external 
        //-                 span Talk to us
</template>

<style lang="stylus" scoped>

    .tutorials__wrapper
        padding-top var(--spacing-10)
        margin-bottom var(--spacing-10)
        border-top 1px solid var(--semi-transparent-color-2)

    .exercises__wrapper
        padding-top var(--spacing-10)
        margin-bottom var(--spacing-10)
        border-top 1px solid var(--semi-transparent-color-2)

    .home
        &__content
            max-width var(--content-max-width-big)
            margin-inline auto

            &__overview
                margin-top 96px
                display flex

                &__title
                    margin-right 16px
                    width 50%

                &__content
                    width 50%
                    margin-top 20px 

                    &__item
                        &:first-child
                            padding-top 0px

            &__intro
                display flex
                align-items center
                margin-top 96px

                &__image
                    margin-left 16px
                    margin-right calc(50% - 50vw)
                    width 50%

                &__content
                    width 100%

                    &__small
                        width 50%

                    &__desc
                        margin-top 20px
                        font-size 21px

                    &__link
                        display flex
                        font-weight 500
                        color var(--background-color-primary)
                        margin-top 32px
                        background var(--color-text)
                        border-radius 10px
                        padding-block 20px
                        padding-inline 60px
                        width fit-content

                        &__icon
                            margin-left 5px
                            width 10px
                            height 10px

    .cards
        display flex
        justify-content space-between
        flex-wrap wrap

        &__wrapper
            max-width 48%
            margin-top var(--spacing-8)
            flex-grow 1
            width 100%

        @media screen and (max-width: 1024px)
            flex-direction column
            flex-wrap nowrap
            
            &__wrapper
                max-width none  

    .tags
        &__description
            font-size 21px
            
        &__list
            display flex
            flex-wrap wrap

            &__item
                cursor pointer
                border-radius 8px
                padding 8px
                flex-shrink 0
                height fit-content
                margin-right 1rem
                margin-block auto
                color white
                opacity .6

                &:hover,
                &:active,
                &__selected
                    opacity 1


    .content
        margin-top var(--spacing-9)
        max-width var(--content-max-width-big)
        margin-inline auto

        &__intro
            &__desc
                margin-top 20px

            &__link
                display flex
                font-weight 500
                color var(--color-text-strong)
                margin-top 20px
                cursor pointer

                &__icon
                    margin-block auto
                    margin-left 5px
                    width 15px
                    height 15px

        &__support

            &__title
                max-width: 35rem

            &__desc
                margin-top 20px

    .tutorials
        &__description
            font-size 21px

    .tools
        display flex
        flex-wrap wrap
        margin-left calc(-1 * var(--spacing-5))
        margin-right calc(-1 * var(--spacing-5))

        &__item
            padding-left var(--spacing-5)
            padding-right var(--spacing-5)
            margin-bottom var(--spacing-5)
            width 50%

            @media screen and (max-width: 480px)
                width 100%
            
            &__container
                padding-top var(--spacing-5)
                padding-bottom var(--spacing-5)
                border-bottom 1px solid var(--semi-transparent-color-2)
                display flex
                height 100%
                margin-block 22px

                @media screen and (max-width: 1024px)
                    flex-direction column

            &__icon
                flex-shrink 0
                width 6.5rem
                margin-bottom 10px
                text-align center
                filter var(--img-filter)

                @media screen and (max-width: 1024px)
                    text-align start

                img
                    width 3.5rem
                    height 3.5rem
                    margin 0
            
            &__content
                padding-bottom var(--spacing-6)

                &__links
                    display flex
                    > *
                        margin-left var(--spacing-6)
                        &:first-child
                            margin-left 0

                    @media screen and (max-width: 480px)
                        flex-direction column
                        
                        .tm-link
                            margin-left 0
                            margin-top 10px
                            width fit-content

    .articles
        display flex
        overflow hidden
        overflow-x auto
        -ms-overflow-style none
        scrollbar-width none

        @media screen and (max-width: 1024px)
            width 100vw
            margin-left calc(50% - 50vw)
            padding-inline calc(50vw - 50%)

        &::-webkit-scrollbar
            display none

        &__item
            padding-inline 15px
            flex 1 1 0px

            &:last-child
                padding-right 0px
            
            &:first-child
                padding-left 0px

            &__container
                background var(--background-color-secondary)
                border-radius 20px
                display flex
                flex-direction column
                height 100%

                @media screen and (min-width: 481px) and (max-width: 1024px)
                    width 40vw

                @media screen and (max-width: 480px)
                    width 80vw

            &__image
                height 0
                padding-bottom 56%
                flex-grow 0
                background-size cover
                border-top-left-radius 20px
                border-top-right-radius 20px

            &__content
                padding 48px
                flex-grow 1
                display flex
                flex-direction column
                justify-content space-between

                @media screen and (min-width: 481px) and (max-width: 1024px)
                    padding 32px

                @media screen and (max-width: 480px)
                    padding 24px

    .link
        margin-block auto
        margin-right 20px
        cursor pointer
        font-weight 500
        color var(--color-text-strong)
        display flex

        &__icon
            margin-left 5px
            width 10px
            height 10px
    
    .tools__wrapper
        margin-top 96px

    .support
        &__card
            background-position right bottom !important

        &__wrapper
            margin-block 96px

    .articles__wrapper
        margin-top 96px

        &__title
            display flex
            justify-content space-between
            align-items center

        .link
            margin-right 0px

    @media screen and (max-width: 480px)
        .tools__wrapper
            margin-top 64px

        .support__wrapper
            margin-block 64px

        .articles__wrapper
            margin-top 64px
        
        .tm-button
            padding-inline 0px
            width 100%

</style>

<script>
export default {
    data() {
        return {
            filterTags: []
        }
    },
    methods: {
        updateFilterTags(tag) {
            if (this.isTagSelected(tag)) {
                const index = this.filterTags.indexOf(tag);
                if (index > -1) {
                    this.filterTags.splice(index, 1);
                }
            } else {
                this.filterTags.push(tag);
            }
        },
        isTagSelected(tag) {
            return this.filterTags?.includes(tag) || false;
        }
    }
}
</script>

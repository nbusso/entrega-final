*ReadMe Entrega Final - Nicolás Busso*

# Cosas a tener en cuenta

- Las páginas jefes.html y personajes.html estan como 'página en construcción', para poder darle un link a las tarjetas del index. El contenido de la consigna sigue siendo 5 html.

- Corregí algunos comentarios e identaciones respecto a lo que venía entregando anteriormente.

- Todas las páginas estan sobre una base de boostrap, y dentro de su contenido principal usé principalmente flex y grid.

- En mundo.html usé un [plugin de boostrap 5 para aplicar Lighbox](https://trvswgnr.github.io/bs5-lightbox/) y crear la galería de imagenes.

- Las imagenes las optimizé en tamaño y peso utilizando [TinyPNG](https://tinypng.com)

# Aplicaciones de consigna

## GRID en clases.html [🔝](#cosas-a-tener-en-cuenta)

```scss
 .profWrapper {
        display: grid;
        grid-template-areas:
        'hipnotizador hipnotizador'
        'guardian guardian'
        'nigromante nigromante'
        'guardabosques guardabosques'
        'elementalista elementalista'
        'guerrero guerrero'
        'ladron ladron'
        'ingeniero ingeniero'
        'retornado retornado';
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(9, auto);
        gap: 20px;

        .profHipnotizador {
            grid-area: hipnotizador;
        }
        
        .profGuardian {
            grid-area: guardian;
        }
        
        .profNigromante {
            grid-area: nigromante;
        }
        
        .profGuardabosques {
            grid-area: guardabosques;
        }
        
        .profElementalista {
            grid-area: elementalista;
        }
        
        .profGuerrero {
            grid-area: guerrero;
        }
        
        .profLadron {
            grid-area: ladron;
        }
        
        .profIngeniero {
            grid-area: ingeniero;
        }
        
        .profRetornado {
            grid-area: retornado;
        }
    }    
```
---
## Boostrap GRID en mundo.html [🔝](#cosas-a-tener-en-cuenta)
```html
    <div class="mainMundo">
        <div class="row g-3 pb-3">
            <a href="../img/screenshots/1.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/1.jpg" class="img-fluid">
            </a>
            <a href="../img/screenshots/2.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/2.jpg" class="img-fluid">
            </a>
            <a href="../img/screenshots/3.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/3.jpg" class="img-fluid">
            </a>
        </div>
        <div class="row g-3 pb-3">
            <a href="../img/screenshots/4.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/4.jpg" class="img-fluid">
            </a>
            <a href="../img/screenshots/5.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/5.jpg" class="img-fluid">
            </a>
            <a href="../img/screenshots/6.jpg" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                <img src="../img/screenshots/6.jpg" class="img-fluid">
            </a>
        </div>
    </div>
    <!-- el código de la galería es mucho más largo pero lo acá lo acorté para una mejor visualización -->
```
---
## Extend [🔝](#cosas-a-tener-en-cuenta)
```scss
//----  variable
%spacing {
    margin: 8em 0 3em 0;
}

//---- algunas aplicaciones
//mundo
.mainMundo {
    @extend %spacing;
}

//jefes
.mainJefes {
    min-height: 80vh;
    @extend %spacing;
}

//personajes
.mainPersonajes {
    min-height: 80vh;
    @extend %spacing;
}
```
---
## Mapas [🔝](#cosas-a-tener-en-cuenta)
```scss
$cards: (
    1: '../img/Concept07.jpg',
    2: '../img/caithe.jpg',
    3: '../img/LegendaryMed.jpg',
    4: '../img/LegendaryLight.jpg',
    5: '../img/boss_1.jpg'
);

@each $number, $img in $cards {
    .card_#{$number} {
        background-image: url($img);
    }
}
```
- lo que compliló en:
```css
.card_1 {
  background-image: url("../img/Concept07.jpg");
}

.card_2 {
  background-image: url("../img/caithe.jpg");
}

.card_3 {
  background-image: url("../img/LegendaryMed.jpg");
}

.card_4 {
  background-image: url("../img/LegendaryLight.jpg");
}

.card_5 {
  background-image: url("../img/boss_1.jpg");
}
```
---
Mixins [🔝](#cosas-a-tener-en-cuenta)
```scss
// en _utilities.scss

@mixin flex-type($dir, $wrap, $just_cont, $align_items) {
    display: flex;
    flex-flow: $dir $wrap;
    justify-content: $just_cont;
    align-items: $align_items;
}

// ejemplo de aplicación en links-utiles
.wrapperCardLinks {
    @include flex-type(row, wrap, center, flex-start);
    margin-top: 4vh;
    gap: 20px;

    .cardLinks {
        border: 1px solid $color_4;
        padding: 2vh 2vw;
        width: 100%;
        max-width: 320px;

        h4 {
            color: $color_2;
        }

        ul {
            padding-left: 20px;

            li {
                line-height: 150%;

                a {
                    color: $color_2;
                }
            }
        }
    }
}
```
 [🔝](#cosas-a-tener-en-cuenta)
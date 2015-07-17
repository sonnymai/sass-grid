# sass-grid

A modifiable responsive grid. 

Uses `flexbox` and gracefully degrades in older browsers, supporting *most* of the same functionality using an `inline-block` grid.
   
## Usage
    
### Using mixins

CSS:

    @import "sass-grid"
    @import "sass-named-breakpoints";
    
    .feature-panel {
      @include grid();
      @include grid--halign-justify-center()
    }
    
    .feature-panel__feature {
      @include grid__unit();
      
      @include named_breakpoint('md') {
        @include grid__unit--cols(3);
      }
      
    }

HTML:
    
    <html class="flexbox"><!-- you'll probably use Modernizr and won't need to manually put this class here --!>
    ...
    
        <div class="feature-panel">
            <div class="feature-panel__feature">Does stuff</div>
            <div class="feature-panel__feature">Does more stuff</div>
            <div class="feature-panel__feature">Does even more stuff</div>
            <div class="feature-panel__feature">It just does all the stuff!</div>
        </div>
        
    ...
    </html>
    
### Using a compiled grid

CSS:

    @import "sass-grid/dist/compiled"
        
HTML:
    
    <html class="flexbox"><!-- you'll probably use Modernizr and won't need to manually put this class here --!>
    ...
    
        <div class="grid" g-xs="halign:justify-center">
            <div class="grid__unit" g-md="cols:3">Does stuff</div>
            <div class="grid__unit" g-md="cols:3">Does more stuff</div>
            <div class="grid__unit" g-md="cols:3">Does even more stuff</div>
            <div class="grid__unit" g-md="cols:3">It just does all the stuff!</div>
        </div>
        
    ...
    </html>
    
## Breakpoints

See [sass-named-breakpoints](https://www.npmjs.com/package/sass-named-breakpoints).
Breakpoints can be defined in the `_breakpoints.scss` partial.

## Building your own grid

1. Requires sass >=3.4
2. Customise the breakpoint settings in `_breakpoint.scss`
3. Run `npm run build`

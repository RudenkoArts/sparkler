## Sparkler  
A modular 2d particle system.

### Features  
* Macro-powered.
* Customizable.
* You can create custom `ParticleModule` to extend functionality.
* Local/World Space rendering.

### Sample Usage  

```haxe

var emitter = new ParticleEmitter<
	ColorOverLifeTimeModule,
	VelocityModule,
	KhaSpriteRendererModule
>({
	cacheSize: 512,
	lifeTime: 2,
	emitterLifeTime: 5,
	emitRate: 50,
	colorOverLifeTime: {
		ease: null,
		list: [
			{
				time: 0,
				value: 0xFFFF0000
			},
			{
				time: 0.5,
				value: 0xFFFF00FF
			},
			{
				time: 1,
				value: 0x00FF00FF
			}
		]
	},
	velocity: {x: 0, y: -200},
	spriteRenderer: {
		image: kha.Assets.images.particle
	},
	sortFunc: function(a, b) {
		return a.age < b.age ? 1 : -1;
	}
});

emitter.start();


```
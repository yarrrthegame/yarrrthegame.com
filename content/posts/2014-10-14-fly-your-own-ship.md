---
title: Fly your own ship
created_at: 2014-10-14
author: Peter Hajdu
kind: article
tags: [Feature]
---

The first fruit of lua integration has been published today.  Ship design is part of the public lua
configuration hosted on github.  [Fork it](http://github.com/yarrrthegame/publicconfig), add your ship,
and send a pull request.

Have a look at the design of the ship you all know already.

~~~ lua

function create_basic_ship()
  return yarrrconfig.create_ship(
    {
      Tile.new( TileCoordinate.new( -1, 0 ), TileCoordinate.new( 2, 0 ) ),
      Tile.new( TileCoordinate.new( 0, 1 ), TileCoordinate.new( 0, 1 ) ),
      Tile.new( TileCoordinate.new( 0, -1 ), TileCoordinate.new( 0, -1 ) )
    },
    {
      Thruster.new( main_thruster, TileCoordinate.new( -1, 0 ), yarrrconfig.degrees( 180 ) ),
      Thruster.new( port_thruster, TileCoordinate.new( 2, 0 ), yarrrconfig.degrees( 90 ) ),
      Thruster.new( starboard_thruster, TileCoordinate.new( 2, 0 ), yarrrconfig.degrees( 270 ) ),
      Canon.new( TileCoordinate.new( 2, 0 ) ),
    })
end
register_object_factory( "ship", create_basic_ship )

~~~

# Define shape
The first table passed to *create_ship* defines the shape of your ship.  Objects in yarrr consist
of tiles defined by their top left and bottom right coordinate.  Imagine the coordinate system as a grid.
A single cell in it is a 5 by 5 metres rectangle.

Some examples:

~~~ lua
  -- a single cell
  Tile.new( TileCoordinate.new( 0, 0 ), TileCoordinate.new( 0, 0 ) )

  -- a 10 by 5 metres tile
  Tile.new( TileCoordinate.new( -1, 0 ), TileCoordinate.new( 0, 0 ) )
~~~

# Define items
The second table describes the items attached to your ship.  The same grid system is used to place
your items.  Your ship is facing 0 degrees on the scratch area.

Item types:

 * thruster( activation key, place on ship, orientation )
 * canon( place on ship )

# Register to the object factory

~~~ lua
register_object_factory( "ship", create_basic_ship )
~~~
The code above registers the *create_basic_ship* function as the factory of type *ship*.


# Trying out your ship
Add your design to *config.lua* and send me a pull request. When I merge your modifications it is deployed
to the server and you can try it out by typing the following command in the terminal of a running client.

~~~ yarrr
/request_ship <ship type>
~~~

At the moment both of the following should work:

~~~ yarrr
/request_ship interceptor
/request_ship duck
~~~

Show me your millenium falcon!


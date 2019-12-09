import { GeoPoint } from './db'

// add Paris to the list of cities and wait for the operation
// to be finished
await db.collection('cities').add({
  name: 'Paris',
  location: new GeoPoint(48.8588377, 2.2770206),
})

// we consider `cities` to be bound to current component
// we retrieve Paris that was just added
const paris = this.cities[this.cities.length - 1]
paris.location.latitude // 48.8588377
paris.location.longitude // 2.2770206
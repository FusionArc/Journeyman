import { Timestamp } from './db'

// Add "La prise de la Bastille" to a list of events
// and wait for th operation to be finished
await db.collection('events').add({
  name: 'Prise de la Bastille',
  date: Timestamp.fromDate(new Date('1789-07-14')),
})

// we consider `events` to be bound to current component
// we retrieve the event we just added
const prise = this.events[this.events.length - 1]
prise.date.seconds // -5694969600
prise.date.nanoseconds // 0
prise.toDate() // Tue Jul 14 1789
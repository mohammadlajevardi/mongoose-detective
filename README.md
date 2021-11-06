const detective = require('mongoose-detective')
const mongoose = require('mongoose')

const InvoiceSchema = new Schema({
  customer: { type: mongoose.Schema.Types.ObjectId, ref: 'Customer' }
})

mongoose.model('Invoice', InvoiceSchema)

const modelName = detective(mongoose.models.Invoice, 'customer')

// modelName = 'Customer'

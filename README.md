# April-month-expense
import { Card, CardContent } from "@/components/ui/card"; import { Progress } from "@/components/ui/progress"; import { motion } from "framer-motion";

export default function ExpensePage() { return ( <div className="min-h-screen bg-gradient-to-br from-orange-100 to-pink-200 p-6 font-sans text-gray-800"> <motion.h1 initial={{ opacity: 0, y: -50 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.8 }} className="text-4xl font-bold text-center mb-8 text-rose-700" > अप्रैल 2025 खर्चा विवरण </motion.h1>

<motion.div
    initial={{ opacity: 0 }}
    animate={{ opacity: 1 }}
    transition={{ delay: 0.5 }}
    className="grid grid-cols-1 md:grid-cols-2 gap-6"
  >
    <Card className="shadow-xl border-none bg-white/70 backdrop-blur-lg">
      <CardContent className="p-6">
        <h2 className="text-xl font-semibold mb-4 text-pink-800">कुल खर्च</h2>
        <p className="text-2xl font-bold">₹8,800</p>
      </CardContent>
    </Card>

    <Card className="shadow-xl border-none bg-white/70 backdrop-blur-lg">
      <CardContent className="p-6">
        <h2 className="text-xl font-semibold mb-4 text-pink-800">मुख्य खर्च</h2>
        <p>किराया + भोजन = ₹6,800 (77%)</p>
        <Progress value={77} className="mt-2" />
        <p className="mt-4">बाकी खर्च = ₹2,000 (23%)</p>
        <Progress value={23} className="mt-2 bg-green-100" />
      </CardContent>
    </Card>
  </motion.div>

  <motion.div
    initial={{ opacity: 0, y: 50 }}
    animate={{ opacity: 1, y: 0 }}
    transition={{ delay: 0.8 }}
    className="mt-10"
  >
    <h2 className="text-2xl font-bold mb-4 text-pink-700">📝 खर्चों की सूची</h2>
    <div className="space-y-4">
      {[
        { item: "किराया", amount: "₹3,500", note: "कमरे का मासिक किराया" },
        { item: "भोजन", amount: "₹3,300", note: "महीने भर का खाना-पीना" },
        { item: "मटका सेट", amount: "₹150", note: "पानी का मटका, स्टैंड और ढक्कन" },
        { item: "अंडरवियर", amount: "₹200", note: "2 चड्डियाँ खरीदीं" },
        { item: "नमकीन", amount: "₹100", note: "स्नैक्स पर खर्च" },
        { item: "मच्छर भगाने वाला", amount: "₹50", note: "ऑल आउट खरीदा" },
        { item: "बिजली बिल", amount: "₹500", note: "इस महीने का बिजली बिल" },
        { item: "यातायात", amount: "₹250", note: "कॉलेज और अन्य जगहों के लिए" },
        { item: "दूध और अन्य", amount: "₹350", note: "दूध पर खर्च" },
        { item: "पानी वाला", amount: "₹150", note: "पानी की सप्लाई के लिए" },
        { item: "मोबाइल रिचार्ज", amount: "₹300", note: "फोन बैलेंस टॉप-अप" },
      ].map((exp, idx) => (
        <Card key={idx} className="bg-white/90 shadow-md border-l-4 border-pink-400">
          <CardContent className="p-4">
            <div className="flex justify-between">
              <span className="font-medium text-gray-700">{exp.item}</span>
              <span className="text-rose-600 font-semibold">{exp.amount}</span>
            </div>
            <p className="text-sm text-gray-500 mt-1">{exp.note}</p>
          </CardContent>
        </Card>
      ))}
    </div>
  </motion.div>

  <motion.div
    initial={{ opacity: 0 }}
    animate={{ opacity: 1 }}
    transition={{ delay: 1 }}
    className="mt-10 p-6 bg-rose-50 border-l-4 border-rose-400 rounded-xl shadow-lg"
  >
    <h2 className="text-lg font-semibold text-rose-700 mb-2">पिताजी के लिए नोट्स</h2>
    <ul className="list-disc pl-5 text-gray-700 space-y-1">
      <li>सारा खर्च जरूरी चीजों पर हुआ है।</li>
      <li>कोई फालतू खर्चा नहीं किया गया।</li>
      <li>अगले महीने छोटे-मोटे खर्चे कम करने की कोशिश करूँगा।</li>
    </ul>
    <p className="mt-4 text-right text-rose-600 font-medium">आपके प्यार के साथ ❤️</p>
  </motion.div>
</div>

); }


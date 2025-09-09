import { AnimatePresence, motion } from "framer-motion";

{/* Confirmation */}
<AnimatePresence>
  {showConfirm && (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
      transition={{ duration: 0.3 }}
      className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center"
      onClick={() => setShowConfirm(false)} // closes on background click
    >
      <motion.div
        initial={{ scale: 0.8, opacity: 0 }}
        animate={{ scale: 1, opacity: 1 }}
        exit={{ scale: 0.8, opacity: 0 }}
        transition={{ type: "spring", stiffness: 300, damping: 20 }}
        className="bg-white rounded-2xl p-6 shadow-lg text-center max-w-sm relative"
        onClick={(e) => e.stopPropagation()} // prevent closing when clicking inside
      >
        <button
          onClick={() => setShowConfirm(false)}
          className="absolute top-2 right-2 text-gray-500 hover:text-gray-700"
        >
          ✖
        </button>
        <h2 className="text-xl font-bold mb-4">You chose all pets! 🎉</h2>
        <p className="mb-4">Click below to continue to Roblox.</p>
        <a
          href="https://www.roblox.com/share?code=80177c63cdc8614aa84be3cbd84b051a&type=Server"
          className="px-6 py-2 bg-blue-500 text-white rounded-xl shadow-md hover:bg-blue-600"
        >
          Continue ➡️
        </a>
      </motion.div>
    </motion.div>
  )}
</AnimatePresence>

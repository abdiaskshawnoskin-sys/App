import React, { useState, useEffect } from 'react';
import { 
  Shield, 
  Zap, 
  Crosshair, 
  Check, 
  ShoppingCart, 
  AlertTriangle, 
  Star, 
  Menu, 
  X,
  Truck,
  Lock,
  ChevronRight
} from 'lucide-react';

const App = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [showAgeGate, setShowAgeGate] = useState(true);

  const handlePurchase = () => {
    document.getElementById('checkout-section').scrollIntoView({ behavior: 'smooth' });
  };

  if (showAgeGate) {
    return (
      <div className="fixed inset-0 z-[100] bg-black flex items-center justify-center p-4">
        <div className="bg-zinc-900 border border-zinc-800 p-8 rounded-2xl max-w-md w-full text-center space-y-6">
          <div className="flex justify-center">
            <Shield className="w-16 h-16 text-red-600" />
          </div>
          <h2 className="text-2xl font-bold text-white uppercase tracking-tighter">Age Verification</h2>
          <p className="text-zinc-400">You must be at least 18 years of age to view this site. The Needler is a high-powered CO2 tool for adult use only.</p>
          <div className="flex flex-col gap-3">
            <button 
              onClick={() => setShowAgeGate(false)}
              className="bg-red-600 hover:bg-red-700 text-white py-4 rounded-xl font-bold transition-all"
            >
              I AM 18+ YEARS OLD
            </button>
            <button 
              onClick={() => window.location.href = "https://google.com"}
              className="text-zinc-500 hover:text-zinc-300 text-sm py-2"
            >
              EXIT SITE
            </button>
          </div>
        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-black text-zinc-100 font-sans selection:bg-red-600 selection:text-white">
      {/* Announcement Bar */}
      <div className="bg-red-600 text-white py-2 text-center text-xs font-bold uppercase tracking-widest px-4">
        Flash Sale: $150 OFF + Free Worldwide Shipping Ends Tonight
      </div>

      {/* Navigation */}
      <nav className="sticky top-0 z-50 bg-black/80 backdrop-blur-md border-b border-zinc-800">
        <div className="max-w-7xl mx-auto px-4 h-16 flex items-center justify-between">
          <div className="flex items-center gap-2">
            <div className="w-8 h-8 bg-red-600 rounded flex items-center justify-center">
              <Crosshair className="text-white w-5 h-5" />
            </div>
            <span className="font-black text-xl tracking-tighter uppercase italic">NEEDLER</span>
          </div>
          
          <div className="hidden md:flex items-center gap-8 text-sm font-medium text-zinc-400">
            <a href="#features" className="hover:text-white transition-colors">Performance</a>
            <a href="#compare" className="hover:text-white transition-colors">Comparison</a>
            <a href="#reviews" className="hover:text-white transition-colors">Reviews</a>
          </div>

          <button 
            onClick={handlePurchase}
            className="bg-zinc-100 text-black px-6 py-2 rounded-full text-sm font-bold hover:bg-red-600 hover:text-white transition-all flex items-center gap-2"
          >
            ORDER NOW
          </button>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="relative pt-12 pb-24 overflow-hidden">
        <div className="max-w-7xl mx-auto px-4 relative z-10">
          <div className="text-center max-w-4xl mx-auto">
            <div className="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-red-600/10 border border-red-600/30 text-red-500 text-xs font-bold mb-6 uppercase tracking-wider">
              <Zap className="w-3 h-3" /> Professional Grade Self-Defense
            </div>
            <h1 className="text-5xl md:text-8xl font-black mb-6 tracking-tighter uppercase italic italic leading-none">
              UNMATCHED POWER.<br/>
              <span className="text-red-600">PREMIUM PROTECTION.</span>
            </h1>
            <p className="text-xl text-zinc-400 mb-10 max-w-2xl mx-auto leading-relaxed">
              Engineered for absolute deterrence. The Needler delivers professional-grade ballistics at half the price of legacy tactical brands.
            </p>
            
            <div className="flex flex-col sm:flex-row items-center justify-center gap-4">
              <button 
                onClick={handlePurchase}
                className="w-full sm:w-auto px-10 py-5 bg-red-600 rounded-2xl font-black text-xl hover:bg-red-700 hover:scale-105 transition-all shadow-[0_0_40px_-10px_rgba(220,38,38,0.5)]"
              >
                GET THE NEEDLER — $250
              </button>
              <div className="flex items-center gap-4 px-6 text-sm text-zinc-500">
                <div className="flex -space-x-2">
                  {[1,2,3,4].map(i => (
                    <div key={i} className="w-8 h-8 rounded-full border-2 border-black bg-zinc-800 flex items-center justify-center text-[8px] font-bold">U{i}</div>
                  ))}
                </div>
                <span>12,000+ Units Shipped</span>
              </div>
            </div>
          </div>

          <div className="mt-20 relative mx-auto max-w-5xl rounded-3xl overflow-hidden border border-zinc-800 shadow-2xl bg-zinc-900 group">
            <div className="aspect-video flex items-center justify-center bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-zinc-800 to-transparent p-12">
               <div className="text-center space-y-4">
                 <Crosshair className="w-32 h-32 text-zinc-700 mx-auto opacity-20" />
                 <p className="text-zinc-500 font-mono text-sm uppercase tracking-widest">[ 4K TACTICAL PRODUCT CINEMATIC ]</p>
               </div>
            </div>
          </div>
        </div>
      </section>

      {/* Comparison Table */}
      <section id="compare" className="py-24 bg-black">
        <div className="max-w-5xl mx-auto px-4">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-black uppercase italic mb-4">The Smart Defender's Choice</h2>
            <p className="text-zinc-400">Superior ballistics without the $500+ markups.</p>
          </div>

          <div className="overflow-x-auto">
            <table className="w-full text-left border-collapse">
              <thead>
                <tr className="border-b border-zinc-800">
                  <th className="py-6 font-bold text-zinc-500 uppercase tracking-widest text-sm">Feature</th>
                  <th className="py-6 px-6 font-black text-red-500 text-lg italic">NEEDLER</th>
                  <th className="py-6 px-6 font-bold text-zinc-500">Legacy Brands</th>
                  <th className="py-6 px-6 font-bold text-zinc-500">Budget Clones</th>
                </tr>
              </thead>
              <tbody className="text-sm">
                {[
                  { label: "Muzzle Velocity", needler: "450+ FPS", comp1: "400 FPS", comp2: "250 FPS" },
                  { label: "Material", needler: "Military Polymer", comp1: "Hardened Steel", comp2: "Injection Plastic" },
                  { label: "Action", needler: "Semi-Auto CO2", comp1: "Single Action", comp2: "Manual Pump" },
                  { label: "Price", needler: "$250.00", comp1: "$595.00+", comp2: "$85.00" },
                ].map((row, idx) => (
                  <tr key={idx} className="border-b border-zinc-900 hover:bg-zinc-900/30 transition-colors">
                    <td className="py-6 text-zinc-400 font-medium">{row.label}</td>
                    <td className="py-6 px-6 font-black text-white">{row.needler}</td>
                    <td className="py-6 px-6 text-zinc-600">{row.comp1}</td>
                    <td className="py-6 px-6 text-zinc-600">{row.comp2}</td>
                  </tr>
                ))}
              </tbody>
            </table>
          </div>
        </div>
      </section>

      {/* Checkout Block */}
      <section id="checkout-section" className="py-24 bg-zinc-900">
        <div className="max-w-6xl mx-auto px-4">
          <div className="bg-black border border-zinc-800 rounded-[3rem] p-8 md:p-16 flex flex-col md:flex-row gap-12 items-center">
            <div className="flex-1 space-y-6">
              <div className="flex items-center gap-2 text-yellow-500">
                {[1,2,3,4,5].map(i => <Star key={i} className="w-5 h-5 fill-current" />)}
                <span className="ml-2 font-bold text-white">Top Rated Security Tool</span>
              </div>
              <h2 className="text-4xl md:text-6xl font-black uppercase italic leading-[0.9]">
                ELITE PROTECTION.<br/>ACCESSIBLE PRICE.
              </h2>
              <div className="flex items-baseline gap-4">
                <span className="text-5xl font-black text-red-600">$250.00</span>
                <span className="text-2xl text-zinc-600 line-through">$399.99</span>
                <span className="bg-red-600/20 text-red-500 px-3 py-1 rounded text-sm font-bold">SALE PRICE</span>
              </div>
              <ul className="space-y-3">
                {["Free Tactical Hard-Shell Case", "3-Year Performance Warranty", "Verified 450+ FPS Output", "Insured Priority Shipping"].map(item => (
                  <li key={item} className="flex items-center gap-3 text-zinc-300">
                    <Check className="w-5 h-5 text-red-600 flex-shrink-0" />
                    <span>{item}</span>
                  </li>
                ))}
              </ul>
            </div>
            
            <div className="w-full max-w-sm bg-zinc-900 p-8 rounded-3xl border border-zinc-800 space-y-6 shadow-2xl">
              <div className="text-center font-bold uppercase tracking-tighter text-zinc-500 mb-2">Secure Checkout</div>
              <button className="w-full bg-red-600 py-5 rounded-2xl font-black text-lg flex items-center justify-center gap-3 hover:bg-red-700 transition-all">
                <ShoppingCart className="w-6 h-6" /> COMPLETE ORDER
              </button>
              <div className="grid grid-cols-2 gap-4 text-[10px] uppercase font-bold text-zinc-500">
                <div className="flex items-center gap-2 border border-zinc-800 p-3 rounded-xl justify-center">
                  <Truck className="w-3 h-3" /> PRIORITY
                </div>
                <div className="flex items-center gap-2 border border-zinc-800 p-3 rounded-xl justify-center">
                  <Lock className="w-3 h-3" /> ENCRYPTED
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Footer Disclaimer */}
      <footer className="bg-black py-16 px-4 border-t border-zinc-900">
        <div className="max-w-7xl mx-auto">
          <div className="p-8 bg-zinc-900/30 rounded-2xl border border-zinc-800/50 flex items-start gap-4 text-zinc-500">
            <AlertTriangle className="w-6 h-6 text-yellow-600 flex-shrink-0" />
            <div className="text-[11px] space-y-2">
              <p className="font-bold uppercase text-zinc-400">Legal Disclaimer</p>
              <p>
                The Needler is a high-kinetic CO2 air gun. Misuse may result in serious injury or death. Always obey local and state laws regarding air-powered devices. This product is for adult use only (18+).
              </p>
            </div>
          </div>
          <div className="mt-8 text-center text-zinc-600 text-xs uppercase tracking-widest">
            © 2026 Needler Tactical Labs.
          </div>
        </div>
      </footer>
    </div>
  );
};

export default App;

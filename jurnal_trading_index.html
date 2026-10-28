import React, { useState, useEffect, useMemo, useRef } from 'react';
import { 
  BarChart2, 
  TrendingUp, 
  TrendingDown, 
  Calendar, 
  PieChart, 
  PlusCircle, 
  Trash2, 
  Edit3, 
  Search, 
  Filter, 
  DollarSign, 
  Percent, 
  Award, 
  Target, 
  Brain, 
  FileText, 
  Download, 
  Upload, 
  RefreshCw, 
  CheckCircle2, 
  XCircle, 
  ChevronLeft, 
  ChevronRight,
  ShieldAlert,
  Sliders,
  Key,
  Link2,
  Lock,
  Eye,
  EyeOff,
  Server,
  FileSpreadsheet,
  Zap,
  Activity,
  Check,
  AlertCircle
} from 'lucide-react';
import { 
  AreaChart, 
  Area, 
  XAxis, 
  YAxis, 
  CartesianGrid, 
  Tooltip, 
  ResponsiveContainer, 
  BarChart, 
  Bar, 
  PieChart as RePieChart, 
  Pie, 
  Cell, 
  Legend 
} from 'recharts';

// --- INITIAL MOCK TRADES DATA ---
const INITIAL_TRADES = [
  {
    id: 'tr-1',
    date: '2026-10-20T10:30',
    pair: 'XAUUSD',
    type: 'LONG',
    strategy: 'Breakout Resistance',
    entryPrice: 2720.50,
    stopLoss: 2712.00,
    takeProfit: 2737.50,
    exitPrice: 2735.00,
    lotSize: 0.5,
    fee: 3.50,
    riskAmount: 50,
    emotion: 'DISCIPLINED',
    notes: 'Entry bagus setelah retest level SNR harian.',
    source: 'MetaTrader 5'
  },
  {
    id: 'tr-2',
    date: '2026-10-21T14:15',
    pair: 'BTCUSDT',
    type: 'SHORT',
    strategy: 'EMA Cross & Rejection',
    entryPrice: 68500,
    stopLoss: 69200,
    takeProfit: 66500,
    exitPrice: 69200,
    lotSize: 0.1,
    fee: 2.00,
    riskAmount: 70,
    emotion: 'FOMO',
    notes: 'Entry terlalu cepat karena takut ketinggalan momen.',
    source: 'Binance API'
  },
  {
    id: 'tr-3',
    date: '2026-10-22T09:00',
    pair: 'EURUSD',
    type: 'SHORT',
    strategy: 'SMC / Order Block',
    entryPrice: 1.0850,
    stopLoss: 1.0875,
    takeProfit: 1.0800,
    exitPrice: 1.0805,
    lotSize: 1.0,
    fee: 4.00,
    riskAmount: 50,
    emotion: 'CALM',
    notes: 'Liquidity sweep di London session.',
    source: 'MetaTrader 4'
  },
  {
    id: 'tr-4',
    date: '2026-10-23T20:00',
    pair: 'XAUUSD',
    type: 'SHORT',
    strategy: 'Scalping',
    entryPrice: 2740.00,
    stopLoss: 2748.00,
    takeProfit: 2724.00,
    exitPrice: 2724.00,
    lotSize: 0.4,
    fee: 3.00,
    riskAmount: 40,
    emotion: 'DISCIPLINED',
    notes: 'TP tersentuh sempurna saat rilis berita inflasi.',
    source: 'Bybit'
  },
  {
    id: 'tr-5',
    date: '2026-10-25T15:30',
    pair: 'GBPUSD',
    type: 'LONG',
    strategy: 'Trend Following',
    entryPrice: 1.2980,
    stopLoss: 1.2940,
    takeProfit: 1.3060,
    exitPrice: 1.3050,
    lotSize: 0.8,
    fee: 3.50,
    riskAmount: 60,
    emotion: 'CALM',
    notes: 'Pola Reversal terkonfirmasi dengan divergence pada RSI.',
    source: 'Manual'
  }
];

const EMOTION_OPTIONS = [
  { value: 'DISCIPLINED', label: 'Disiplin', color: 'bg-emerald-500/20 text-emerald-400 border-emerald-500/30' },
  { value: 'CALM', label: 'Tenang', color: 'bg-blue-500/20 text-blue-400 border-blue-500/30' },
  { value: 'PATIENT', label: 'Sabar', color: 'bg-indigo-500/20 text-indigo-400 border-indigo-500/30' },
  { value: 'FOMO', label: 'FOMO', color: 'bg-amber-500/20 text-amber-400 border-amber-500/30' },
  { value: 'GREED', label: 'Tamak (Greed)', color: 'bg-purple-500/20 text-purple-400 border-purple-500/30' },
  { value: 'REVENGE', label: 'Revenge Trade', color: 'bg-rose-500/20 text-rose-400 border-rose-500/30' },
  { value: 'ANXIOUS', label: 'Cemas/Ragu', color: 'bg-orange-500/20 text-orange-400 border-orange-500/30' }
];

const STRATEGIES = [
  'Breakout Resistance',
  'EMA Cross & Rejection',
  'SMC / Order Block',
  'Scalping',
  'Trend Following',
  'Fair Value Gap (FVG)',
  'Pullback Swing',
  'Lainnya'
];

const BROKERS = [
  { id: 'mt5', name: 'MetaTrader 5 (MT5)', type: 'Forex / Metals', icon: '📈' },
  { id: 'mt4', name: 'MetaTrader 4 (MT4)', type: 'Forex / Commodities', icon: '📉' },
  { id: 'binance', name: 'Binance Futures / Spot', type: 'Crypto', icon: '🟡' },
  { id: 'bybit', name: 'Bybit Unified Account', type: 'Crypto Derivatives', icon: '⚫' },
  { id: 'oanda', name: 'OANDA API v20', type: 'Forex CFD', icon: '🔵' },
  { id: 'okx', name: 'OKX API', type: 'Crypto / Swap', icon: '⚪' }
];

export default function App() {
  // --- STATES ---
  const [trades, setTrades] = useState(() => {
    const saved = localStorage.getItem('rt_trading_trades_v2');
    return saved ? JSON.parse(saved) : INITIAL_TRADES;
  });

  const [activeTab, setActiveTab] = useState('dashboard'); // dashboard, journal, calendar, api, import
  const [initialBalance, setInitialBalance] = useState(() => {
    const saved = localStorage.getItem('rt_trading_balance_v2');
    return saved ? parseFloat(saved) : 5000;
  });

  // Modal State
  const [isModalOpen, setIsModalOpen] = useState(false);
  const [editingTrade, setEditingTrade] = useState(null);

  // Filter States
  const [searchTerm, setSearchTerm] = useState('');
  const [filterPair, setFilterPair] = useState('ALL');
  const [filterResult, setFilterResult] = useState('ALL');
  const [filterStrategy, setFilterStrategy] = useState('ALL');

  // Calendar State
  const [currentCalendarDate, setCurrentCalendarDate] = useState(new Date(2026, 9, 1));

  // --- API & CONNECTION STATES ---
  const [apiConfig, setApiConfig] = useState(() => {
    const saved = localStorage.getItem('rt_api_config');
    return saved ? JSON.parse(saved) : {
      broker: 'mt5',
      apiKey: '',
      apiSecret: '',
      server: 'MetaQuotes-Demo',
      passphrase: '',
      isConnected: false,
      autoSync: true,
      lastSynced: null
    };
  });
  const [showSecret, setShowSecret] = useState(false);
  const [isSyncing, setIsSyncing] = useState(false);

  // --- CSV IMPORTER STATE ---
  const [csvText, setCsvText] = useState('');
  const [importNotice, setImportNotice] = useState(null);
  const fileInputRef = useRef(null);

  // Form State Manual
  const [formData, setFormData] = useState({
    date: new Date().toISOString().slice(0, 16),
    pair: 'XAUUSD',
    type: 'LONG',
    strategy: 'Breakout Resistance',
    entryPrice: '',
    stopLoss: '',
    takeProfit: '',
    exitPrice: '',
    lotSize: '0.1',
    fee: '0',
    riskAmount: '50',
    emotion: 'DISCIPLINED',
    notes: '',
    source: 'Manual'
  });

  // LocalStorage Persistence
  useEffect(() => {
    localStorage.setItem('rt_trading_trades_v2', JSON.stringify(trades));
  }, [trades]);

  useEffect(() => {
    localStorage.setItem('rt_trading_balance_v2', initialBalance.toString());
  }, [initialBalance]);

  useEffect(() => {
    localStorage.setItem('rt_api_config', JSON.stringify(apiConfig));
  }, [apiConfig]);

  // Trade PnL & Metrics Calculation
  const calculateTradeMetrics = (t) => {
    const entry = parseFloat(t.entryPrice) || 0;
    const exit = parseFloat(t.exitPrice) || 0;
    const size = parseFloat(t.lotSize) || 0;
    const fee = parseFloat(t.fee) || 0;
    const risk = parseFloat(t.riskAmount) || 1;

    if (!entry || !exit) return { pnl: 0, pnlPercent: 0, rMultiple: 0 };

    let contractFactor = 100;
    if (t.pair.includes('BTC') || t.pair.includes('ETH') || t.pair.includes('USDT')) contractFactor = 1;
    if (t.pair.includes('.JK')) contractFactor = 100;

    let pnl = 0;
    if (t.type === 'LONG') {
      pnl = (exit - entry) * size * contractFactor - fee;
    } else {
      pnl = (entry - exit) * size * contractFactor - fee;
    }

    const pnlPercent = (pnl / Math.max(initialBalance, 1)) * 100;
    const rMultiple = risk > 0 ? (pnl / risk) : 0;

    return {
      pnl: parseFloat(pnl.toFixed(2)),
      pnlPercent: parseFloat(pnlPercent.toFixed(2)),
      rMultiple: parseFloat(rMultiple.toFixed(2))
    };
  };

  const enrichedTrades = useMemo(() => {
    return trades.map(t => ({
      ...t,
      ...calculateTradeMetrics(t)
    })).sort((a, b) => new Date(b.date) - new Date(a.date));
  }, [trades, initialBalance]);

  // Overall Performance Statistics
  const stats = useMemo(() => {
    const totalTrades = enrichedTrades.length;
    if (totalTrades === 0) return {
      totalTrades: 0, winCount: 0, lossCount: 0, winRate: 0,
      totalPnL: 0, netProfit: 0, profitFactor: 0, avgRR: 0,
      currBalance: initialBalance
    };

    let totalPnL = 0;
    let totalWins = 0;
    let totalLosses = 0;
    let winCount = 0;
    let lossCount = 0;
    let totalR = 0;

    enrichedTrades.forEach(t => {
      totalPnL += t.pnl;
      totalR += t.rMultiple;
      if (t.pnl > 0) {
        totalWins += t.pnl;
        winCount++;
      } else if (t.pnl < 0) {
        totalLosses += Math.abs(t.pnl);
        lossCount++;
      }
    });

    const winRate = ((winCount / totalTrades) * 100).toFixed(1);
    const profitFactor = totalLosses > 0 ? (totalWins / totalLosses).toFixed(2) : totalWins > 0 ? 'Inf' : '0';
    const avgRR = (totalR / totalTrades).toFixed(2);
    const currBalance = initialBalance + totalPnL;

    return {
      totalTrades,
      winCount,
      lossCount,
      winRate,
      totalPnL: totalPnL.toFixed(2),
      netProfit: totalPnL,
      profitFactor,
      avgRR,
      currBalance: currBalance.toFixed(2)
    };
  }, [enrichedTrades, initialBalance]);

  // Equity Curve Data
  const equityData = useMemo(() => {
    const sorted = [...enrichedTrades].sort((a, b) => new Date(a.date) - new Date(b.date));
    let cumBalance = initialBalance;
    
    return [
      { name: 'Start', balance: initialBalance, date: 'Awal' },
      ...sorted.map((t, idx) => {
        cumBalance += t.pnl;
        return {
          name: `#${idx + 1}`,
          balance: parseFloat(cumBalance.toFixed(2)),
          pnl: t.pnl,
          pair: t.pair,
          date: new Date(t.date).toLocaleDateString('id-ID', { month: 'short', day: 'numeric' })
        };
      })
    ];
  }, [enrichedTrades, initialBalance]);

  // Pair Performance Analytics Data
  const pairPerformance = useMemo(() => {
    const map = {};
    enrichedTrades.forEach(t => {
      if (!map[t.pair]) map[t.pair] = { pair: t.pair, pnl: 0, trades: 0 };
      map[t.pair].pnl += t.pnl;
      map[t.pair].trades += 1;
    });

    return Object.values(map).map(p => ({
      ...p,
      pnl: parseFloat(p.pnl.toFixed(2))
    }));
  }, [enrichedTrades]);

  // Emotion Analytics Data
  const emotionPerformance = useMemo(() => {
    const map = {};
    enrichedTrades.forEach(t => {
      const emo = t.emotion || 'DISCIPLINED';
      if (!map[emo]) map[emo] = { emotion: emo, pnl: 0, count: 0 };
      map[emo].pnl += t.pnl;
      map[emo].count += 1;
    });

    return Object.values(map).map(e => ({
      ...e,
      pnl: parseFloat(e.pnl.toFixed(2)),
      label: EMOTION_OPTIONS.find(o => o.value === e.emotion)?.label || e.emotion
    }));
  }, [enrichedTrades]);

  // --- API SYNC MOCK HANDLER ---
  const handleConnectAPI = () => {
    setIsSyncing(true);
    setTimeout(() => {
      setApiConfig(prev => ({
        ...prev,
        isConnected: true,
        lastSynced: new Date().toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' })
      }));
      setIsSyncing(false);
    }, 1200);
  };

  const handleDisconnectAPI = () => {
    setApiConfig(prev => ({ ...prev, isConnected: false }));
  };

  const handleSyncNow = () => {
    setIsSyncing(true);
    setTimeout(() => {
      // Simulate fetching 1 new live trade from broker
      const livePairs = ['XAUUSD', 'BTCUSDT', 'EURUSD', 'ETHUSDT'];
      const randomPair = livePairs[Math.floor(Math.random() * livePairs.length)];
      const isWin = Math.random() > 0.4;
      const pnlAmt = isWin ? (Math.random() * 80 + 20) : -(Math.random() * 40 + 10);
      
      const newLiveTrade = {
        id: `api-sync-${Date.now()}`,
        date: new Date().toISOString().slice(0, 16),
        pair: randomPair,
        type: Math.random() > 0.5 ? 'LONG' : 'SHORT',
        strategy: 'Auto Sync API',
        entryPrice: randomPair.includes('BTC') ? 68000 : 2730,
        exitPrice: randomPair.includes('BTC') ? (isWin ? 68800 : 67500) : (isWin ? 2742 : 2720),
        stopLoss: 2715,
        takeProfit: 2750,
        lotSize: 0.2,
        fee: 2.5,
        riskAmount: 50,
        emotion: 'DISCIPLINED',
        notes: `Trade otomatis di-synchronize dari ${BROKERS.find(b=>b.id===apiConfig.broker)?.name || 'API Broker'}`,
        source: BROKERS.find(b=>b.id===apiConfig.broker)?.name || 'API Sync'
      };

      setTrades(prev => [newLiveTrade, ...prev]);
      setApiConfig(prev => ({
        ...prev,
        lastSynced: new Date().toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' })
      }));
      setIsSyncing(false);
    }, 1500);
  };

  // --- CSV PARSER HANDLER ---
  const handleParseCSV = (rawText) => {
    try {
      const lines = rawText.trim().split('\n');
      if (lines.length < 2) {
        setImportNotice({ type: 'error', text: 'Format file tidak valid atau kosong.' });
        return;
      }

      const newParsedTrades = [];
      // Skip header line
      for (let i = 1; i < lines.length; i++) {
        const cols = lines[i].split(',').map(c => c.trim().replace(/^"(.*)"$/, '$1'));
        if (cols.length >= 5) {
          // Format expected: Date, Pair, Type, Entry, Exit, Lot, Fee, Notes
          const [dateStr, pair, type, entry, exit, lot, fee, notes] = cols;
          if (pair && entry && exit) {
            newParsedTrades.push({
              id: `csv-${Date.now()}-${i}`,
              date: dateStr ? new Date(dateStr).toISOString().slice(0, 16) : new Date().toISOString().slice(0, 16),
              pair: pair.toUpperCase(),
              type: (type && type.toUpperCase().includes('SHORT')) ? 'SHORT' : 'LONG',
              strategy: 'CSV Import',
              entryPrice: parseFloat(entry) || 0,
              exitPrice: parseFloat(exit) || 0,
              stopLoss: 0,
              takeProfit: 0,
              lotSize: parseFloat(lot) || 0.1,
              fee: parseFloat(fee) || 0,
              riskAmount: 50,
              emotion: 'CALM',
              notes: notes || 'Diimpor dari berkas CSV/Statement',
              source: 'CSV File'
            });
          }
        }
      }

      if (newParsedTrades.length > 0) {
        setTrades(prev => [...newParsedTrades, ...prev]);
        setImportNotice({ type: 'success', text: `Berhasil mengimpor ${newParsedTrades.length} catatan transaksi!` });
        setCsvText('');
      } else {
        setImportNotice({ type: 'error', text: 'Tidak dapat menemukan transaksi yang cocok. Pastikan kolom sesuai.' });
      }
    } catch (err) {
      setImportNotice({ type: 'error', text: 'Gagal memproses file CSV: ' + err.message });
    }
  };

  const handleFileUpload = (e) => {
    const file = e.target.files[0];
    if (!file) return;

    const reader = new FileReader();
    reader.onload = (event) => {
      const content = event.target.result;
      handleParseCSV(content);
    };
    reader.readAsText(file);
  };

  // Handlers Modal
  const handleOpenAddModal = () => {
    setEditingTrade(null);
    setFormData({
      date: new Date().toISOString().slice(0, 16),
      pair: 'XAUUSD',
      type: 'LONG',
      strategy: STRATEGIES[0],
      entryPrice: '',
      stopLoss: '',
      takeProfit: '',
      exitPrice: '',
      lotSize: '0.1',
      fee: '0',
      riskAmount: '50',
      emotion: 'DISCIPLINED',
      notes: '',
      source: 'Manual'
    });
    setIsModalOpen(true);
  };

  const handleOpenEditModal = (trade) => {
    setEditingTrade(trade.id);
    setFormData({ ...trade });
    setIsModalOpen(true);
  };

  const handleDeleteTrade = (id) => {
    if (window.confirm('Apakah Anda yakin ingin menghapus catatan trade ini?')) {
      setTrades(trades.filter(t => t.id !== id));
    }
  };

  const handleFormSubmit = (e) => {
    e.preventDefault();
    if (editingTrade) {
      setTrades(trades.map(t => t.id === editingTrade ? { ...formData, id: editingTrade } : t));
    } else {
      const newTrade = { ...formData, id: `tr-${Date.now()}` };
      setTrades([newTrade, ...trades]);
    }
    setIsModalOpen(false);
  };

  const handleResetData = () => {
    if (window.confirm('Reset data akan mengembalikan ke data sampel awal. Lanjutkan?')) {
      setTrades(INITIAL_TRADES);
      setInitialBalance(5000);
      localStorage.removeItem('rt_trading_trades_v2');
      localStorage.removeItem('rt_trading_balance_v2');
    }
  };

  // Filtered List
  const filteredTrades = useMemo(() => {
    return enrichedTrades.filter(t => {
      const matchSearch = t.pair.toLowerCase().includes(searchTerm.toLowerCase()) ||
                          t.strategy.toLowerCase().includes(searchTerm.toLowerCase()) ||
                          t.notes.toLowerCase().includes(searchTerm.toLowerCase());
      const matchPair = filterPair === 'ALL' || t.pair === filterPair;
      const matchStrategy = filterStrategy === 'ALL' || t.strategy === filterStrategy;
      const matchResult = filterResult === 'ALL' ? true :
                          filterResult === 'WIN' ? t.pnl > 0 :
                          filterResult === 'LOSS' ? t.pnl < 0 : t.pnl === 0;

      return matchSearch && matchPair && matchStrategy && matchResult;
    });
  }, [enrichedTrades, searchTerm, filterPair, filterStrategy, filterResult]);

  const uniquePairs = useMemo(() => Array.from(new Set(trades.map(t => t.pair))), [trades]);

  return (
    <div className="min-h-screen bg-slate-950 text-slate-100 flex flex-col font-sans">
      {/* HEADER NAVBAR */}
      <header className="bg-slate-900 border-b border-slate-800 sticky top-0 z-30 px-4 lg:px-8 py-3 flex flex-wrap items-center justify-between gap-4">
        <div className="flex items-center gap-3">
          <div className="bg-gradient-to-tr from-emerald-500 to-cyan-500 p-2.5 rounded-xl shadow-lg shadow-emerald-500/10">
            <TrendingUp className="w-6 h-6 text-slate-950 stroke-[2.5]" />
          </div>
          <div>
            <h1 className="text-xl font-bold tracking-tight bg-gradient-to-r from-white via-slate-200 to-slate-400 bg-clip-text text-transparent">
              Rekap Trading Pro
            </h1>
            <div className="flex items-center gap-2 mt-0.5">
              <span className="text-xs text-slate-400">Jurnal & API Sync</span>
              {apiConfig.isConnected ? (
                <span className="inline-flex items-center gap-1 px-2 py-0.5 rounded-full text-[10px] font-bold bg-emerald-500/20 text-emerald-400 border border-emerald-500/30">
                  <span className="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-pulse" /> Live API Connected
                </span>
              ) : (
                <span className="inline-flex items-center gap-1 px-2 py-0.5 rounded-full text-[10px] font-medium bg-slate-800 text-slate-400 border border-slate-700">
                  Manual Mode
                </span>
              )}
            </div>
          </div>
        </div>

        {/* Global Stats Bar */}
        <div className="hidden xl:flex items-center gap-6 bg-slate-950/60 border border-slate-800/80 rounded-xl px-4 py-2 text-xs">
          <div>
            <span className="text-slate-400 block">Modal Awal</span>
            <div className="flex items-center gap-1.5 font-semibold text-slate-200">
              <span>$</span>
              <input 
                type="number" 
                value={initialBalance} 
                onChange={(e) => setInitialBalance(parseFloat(e.target.value) || 0)}
                className="w-20 bg-transparent border-b border-slate-700 text-slate-200 text-xs focus:outline-none focus:border-emerald-500"
              />
            </div>
          </div>
          <div className="w-px h-7 bg-slate-800" />
          <div>
            <span className="text-slate-400 block">Saldo Saat Ini</span>
            <span className={`font-bold ${stats.netProfit >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
              ${stats.currBalance}
            </span>
          </div>
          <div className="w-px h-7 bg-slate-800" />
          <div>
            <span className="text-slate-400 block">Total Net PnL</span>
            <span className={`font-bold ${stats.netProfit >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
              {stats.netProfit >= 0 ? `+$${stats.totalPnL}` : `-$${Math.abs(stats.totalPnL)}`}
            </span>
          </div>
        </div>

        {/* Action Controls */}
        <div className="flex items-center gap-2.5">
          {apiConfig.isConnected && (
            <button
              onClick={handleSyncNow}
              disabled={isSyncing}
              className="flex items-center gap-1.5 bg-slate-800 hover:bg-slate-700 text-emerald-400 font-medium px-3 py-2 rounded-xl border border-slate-700 text-xs transition cursor-pointer"
            >
              <RefreshCw className={`w-3.5 h-3.5 ${isSyncing ? 'animate-spin text-emerald-400' : ''}`} />
              <span>{isSyncing ? 'Syncing...' : 'Sync Now'}</span>
            </button>
          )}

          <button 
            onClick={handleOpenAddModal}
            className="flex items-center gap-2 bg-emerald-500 hover:bg-emerald-600 active:bg-emerald-700 text-slate-950 font-semibold px-4 py-2 rounded-xl transition-all shadow-lg shadow-emerald-500/20 text-sm cursor-pointer"
          >
            <PlusCircle className="w-4 h-4 stroke-[2.5]" />
            <span>Tambah Trade</span>
          </button>

          <button
            onClick={handleResetData}
            title="Reset Data ke Default"
            className="p-2 text-slate-400 hover:text-slate-200 hover:bg-slate-800 rounded-xl transition border border-slate-800"
          >
            <RefreshCw className="w-4 h-4" />
          </button>
        </div>
      </header>

      {/* NAVIGATION TABS */}
      <div className="bg-slate-900/60 border-b border-slate-800/80 px-4 lg:px-8">
        <nav className="flex space-x-1 overflow-x-auto py-2 scrollbar-none">
          {[
            { id: 'dashboard', label: 'Dashboard Rekap', icon: BarChart2 },
            { id: 'journal', label: 'Jurnal Trade', icon: FileText },
            { id: 'calendar', label: 'Kalender PnL', icon: Calendar },
            { id: 'analytics', label: 'Psikologi & Analytics', icon: Brain },
            { id: 'api', label: 'Koneksi API Broker', icon: Link2, badge: apiConfig.isConnected ? 'Connected' : null },
            { id: 'import', label: 'Impor CSV / Statement', icon: Upload }
          ].map((tab) => {
            const Icon = tab.icon;
            const active = activeTab === tab.id;
            return (
              <button
                key={tab.id}
                onClick={() => setActiveTab(tab.id)}
                className={`flex items-center gap-2 px-4 py-2 rounded-xl text-sm font-medium transition-all cursor-pointer whitespace-nowrap ${
                  active
                    ? 'bg-slate-800 text-emerald-400 shadow-sm border border-slate-700/60'
                    : 'text-slate-400 hover:text-slate-200 hover:bg-slate-800/40'
                }`}
              >
                <Icon className={`w-4 h-4 ${active ? 'text-emerald-400' : 'text-slate-400'}`} />
                <span>{tab.label}</span>
                {tab.badge && (
                  <span className="ml-1 text-[10px] bg-emerald-500/20 text-emerald-400 px-1.5 py-0.5 rounded-md font-bold">
                    {tab.badge}
                  </span>
                )}
              </button>
            );
          })}
        </nav>
      </div>

      {/* MAIN CONTENT AREA */}
      <main className="flex-1 p-4 lg:p-8 max-w-7xl w-full mx-auto space-y-6">

        {/* ==================== TAB 1: DASHBOARD ==================== */}
        {activeTab === 'dashboard' && (
          <div className="space-y-6">
            {/* KPI STATS CARDS */}
            <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-3 lg:gap-4">
              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Win Rate</span>
                  <Award className="w-4 h-4 text-emerald-400" />
                </div>
                <div className="mt-3">
                  <div className="text-2xl font-bold text-slate-100">{stats.winRate}%</div>
                  <div className="text-[11px] text-slate-400 mt-1 flex items-center gap-1">
                    <span className="text-emerald-400 font-semibold">{stats.winCount}W</span> / 
                    <span className="text-rose-400 font-semibold">{stats.lossCount}L</span>
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Net Profit</span>
                  <DollarSign className={`w-4 h-4 ${stats.netProfit >= 0 ? 'text-emerald-400' : 'text-rose-400'}`} />
                </div>
                <div className="mt-3">
                  <div className={`text-2xl font-bold ${stats.netProfit >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
                    {stats.netProfit >= 0 ? `+$${stats.totalPnL}` : `-$${Math.abs(stats.totalPnL)}`}
                  </div>
                  <div className="text-[11px] text-slate-400 mt-1">
                    ROI: {((stats.netProfit / initialBalance) * 100).toFixed(1)}%
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Total Trades</span>
                  <BarChart2 className="w-4 h-4 text-cyan-400" />
                </div>
                <div className="mt-3">
                  <div className="text-2xl font-bold text-slate-100">{stats.totalTrades}</div>
                  <div className="text-[11px] text-slate-400 mt-1">
                    Posisi Eksekusi
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Profit Factor</span>
                  <Target className="w-4 h-4 text-indigo-400" />
                </div>
                <div className="mt-3">
                  <div className="text-2xl font-bold text-slate-100">{stats.profitFactor}</div>
                  <div className="text-[11px] text-slate-400 mt-1">
                    Gross Win / Loss
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Avg R:R</span>
                  <Percent className="w-4 h-4 text-amber-400" />
                </div>
                <div className="mt-3">
                  <div className="text-2xl font-bold text-slate-100">{stats.avgRR}R</div>
                  <div className="text-[11px] text-slate-400 mt-1">
                    Rasio Rata-rata
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col justify-between">
                <div className="flex items-center justify-between text-slate-400 text-xs font-medium">
                  <span>Saldo Akun</span>
                  <Sliders className="w-4 h-4 text-purple-400" />
                </div>
                <div className="mt-3">
                  <div className="text-2xl font-bold text-slate-100">${stats.currBalance}</div>
                  <div className="text-[11px] text-slate-400 mt-1">
                    Modal: ${initialBalance}
                  </div>
                </div>
              </div>
            </div>

            {/* CHARTS SECTION */}
            <div className="grid grid-cols-1 lg:grid-cols-3 gap-6">
              <div className="lg:col-span-2 bg-slate-900 border border-slate-800 rounded-2xl p-5 flex flex-col justify-between">
                <div className="flex items-center justify-between mb-4">
                  <div>
                    <h3 className="font-bold text-slate-200">Equity Curve & Pertumbuhan Modal</h3>
                    <p className="text-xs text-slate-400">Kumulatif saldo akun setelah tiap eksekusi trade</p>
                  </div>
                </div>

                <div className="h-72 w-full">
                  <ResponsiveContainer width="100%" height="100%">
                    <AreaChart data={equityData} margin={{ top: 10, right: 10, left: -20, bottom: 0 }}>
                      <defs>
                        <linearGradient id="equityGrad" x1="0" y1="0" x2="0" y2="1">
                          <stop offset="5%" stopColor="#10b981" stopOpacity={0.3}/>
                          <stop offset="95%" stopColor="#10b981" stopOpacity={0}/>
                        </linearGradient>
                      </defs>
                      <CartesianGrid strokeDasharray="3 3" stroke="#1e293b" vertical={false} />
                      <XAxis dataKey="name" stroke="#64748b" fontSize={11} tickLine={false} />
                      <YAxis stroke="#64748b" fontSize={11} tickLine={false} domain={['dataMin - 100', 'dataMax + 100']} />
                      <Tooltip 
                        contentStyle={{ backgroundColor: '#0f172a', borderColor: '#334155', borderRadius: '0.75rem', color: '#f8fafc' }}
                        formatter={(val) => [`$${val}`, 'Saldo']}
                      />
                      <Area type="monotone" dataKey="balance" stroke="#10b981" strokeWidth={2.5} fillOpacity={1} fill="url(#equityGrad)" />
                    </AreaChart>
                  </ResponsiveContainer>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-5 flex flex-col">
                <div className="mb-4">
                  <h3 className="font-bold text-slate-200">Performa Per Pair</h3>
                  <p className="text-xs text-slate-400">Total PnL per pasangan aset</p>
                </div>

                <div className="h-72 w-full">
                  <ResponsiveContainer width="100%" height="100%">
                    <BarChart data={pairPerformance} margin={{ top: 10, right: 10, left: -20, bottom: 0 }}>
                      <CartesianGrid strokeDasharray="3 3" stroke="#1e293b" vertical={false} />
                      <XAxis dataKey="pair" stroke="#64748b" fontSize={11} tickLine={false} />
                      <YAxis stroke="#64748b" fontSize={11} tickLine={false} />
                      <Tooltip 
                        contentStyle={{ backgroundColor: '#0f172a', borderColor: '#334155', borderRadius: '0.75rem', color: '#f8fafc' }}
                        formatter={(val) => [`$${val}`, 'Net PnL']}
                      />
                      <Bar dataKey="pnl" radius={[6, 6, 0, 0]}>
                        {pairPerformance.map((entry, index) => (
                          <Cell key={`cell-${index}`} fill={entry.pnl >= 0 ? '#10b981' : '#f43f5e'} />
                        ))}
                      </Bar>
                    </BarChart>
                  </ResponsiveContainer>
                </div>
              </div>
            </div>

            {/* RECENT TRADES PREVIEW */}
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-5 space-y-4">
              <div className="flex items-center justify-between">
                <div>
                  <h3 className="font-bold text-slate-200">Riwayat Trade Terakhir</h3>
                  <p className="text-xs text-slate-400">5 transaksi terbaru yang tersimpan</p>
                </div>
                <button 
                  onClick={() => setActiveTab('journal')}
                  className="text-xs text-emerald-400 hover:text-emerald-300 font-medium flex items-center gap-1 cursor-pointer"
                >
                  Lihat Semua Jurnal →
                </button>
              </div>

              <div className="overflow-x-auto">
                <table className="w-full text-left text-sm text-slate-300">
                  <thead className="text-xs text-slate-400 bg-slate-950/50 uppercase border-b border-slate-800">
                    <tr>
                      <th className="py-3 px-4">Tanggal</th>
                      <th className="py-3 px-4">Pair</th>
                      <th className="py-3 px-4">Tipe</th>
                      <th className="py-3 px-4">Sumber</th>
                      <th className="py-3 px-4">Entry / Exit</th>
                      <th className="py-3 px-4 text-right">PnL ($)</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-slate-800/60">
                    {enrichedTrades.slice(0, 5).map((t) => (
                      <tr key={t.id} className="hover:bg-slate-800/30 transition">
                        <td className="py-3 px-4 text-xs whitespace-nowrap">
                          {new Date(t.date).toLocaleDateString('id-ID', { day: '2-digit', month: 'short', hour: '2-digit', minute: '2-digit' })}
                        </td>
                        <td className="py-3 px-4 font-semibold text-slate-100">{t.pair}</td>
                        <td className="py-3 px-4">
                          <span className={`px-2 py-0.5 text-[10px] font-bold rounded-md ${
                            t.type === 'LONG' ? 'bg-emerald-500/20 text-emerald-400 border border-emerald-500/30' : 'bg-rose-500/20 text-rose-400 border border-rose-500/30'
                          }`}>
                            {t.type}
                          </span>
                        </td>
                        <td className="py-3 px-4 text-xs">
                          <span className="text-slate-400 bg-slate-950 px-2 py-0.5 rounded border border-slate-800">
                            {t.source || 'Manual'}
                          </span>
                        </td>
                        <td className="py-3 px-4 text-xs font-mono">
                          {t.entryPrice} → {t.exitPrice}
                        </td>
                        <td className={`py-3 px-4 font-bold text-right font-mono ${t.pnl >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
                          {t.pnl >= 0 ? `+$${t.pnl}` : `-$${Math.abs(t.pnl)}`}
                        </td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        )}

        {/* ==================== TAB 2: JURNAL TRADE ==================== */}
        {activeTab === 'journal' && (
          <div className="space-y-6">
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-wrap items-center justify-between gap-4">
              <div className="relative flex-1 min-w-[200px]">
                <Search className="w-4 h-4 text-slate-500 absolute left-3 top-1/2 -translate-y-1/2" />
                <input
                  type="text"
                  placeholder="Cari pair, strategi, catatan..."
                  value={searchTerm}
                  onChange={(e) => setSearchTerm(e.target.value)}
                  className="w-full bg-slate-950 border border-slate-800 rounded-xl pl-9 pr-4 py-2 text-sm text-slate-200 placeholder-slate-500 focus:outline-none focus:border-emerald-500"
                />
              </div>

              <div className="flex flex-wrap items-center gap-2">
                <select
                  value={filterPair}
                  onChange={(e) => setFilterPair(e.target.value)}
                  className="bg-slate-950 border border-slate-800 text-slate-300 text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-emerald-500"
                >
                  <option value="ALL">Semua Pair</option>
                  {uniquePairs.map(p => <option key={p} value={p}>{p}</option>)}
                </select>

                <select
                  value={filterResult}
                  onChange={(e) => setFilterResult(e.target.value)}
                  className="bg-slate-950 border border-slate-800 text-slate-300 text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-emerald-500"
                >
                  <option value="ALL">Semua Hasil</option>
                  <option value="WIN">Win (Profit)</option>
                  <option value="LOSS">Loss (Rugi)</option>
                </select>

                <select
                  value={filterStrategy}
                  onChange={(e) => setFilterStrategy(e.target.value)}
                  className="bg-slate-950 border border-slate-800 text-slate-300 text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-emerald-500"
                >
                  <option value="ALL">Semua Strategi</option>
                  {STRATEGIES.map(s => <option key={s} value={s}>{s}</option>)}
                </select>
              </div>
            </div>

            <div className="bg-slate-900 border border-slate-800 rounded-2xl overflow-hidden shadow-xl">
              <div className="overflow-x-auto">
                <table className="w-full text-left text-sm text-slate-300">
                  <thead className="text-xs text-slate-400 bg-slate-950/80 uppercase border-b border-slate-800">
                    <tr>
                      <th className="py-3.5 px-4">Waktu</th>
                      <th className="py-3.5 px-4">Pair</th>
                      <th className="py-3.5 px-4">Posisi</th>
                      <th className="py-3.5 px-4">Strategi</th>
                      <th className="py-3.5 px-4">Harga Entry / Exit</th>
                      <th className="py-3.5 px-4">Sumber</th>
                      <th className="py-3.5 px-4 text-right">PnL ($)</th>
                      <th className="py-3.5 px-4 text-right">R-Mult</th>
                      <th className="py-3.5 px-4 text-center">Aksi</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-slate-800/60">
                    {filteredTrades.length === 0 ? (
                      <tr>
                        <td colSpan="9" className="text-center py-12 text-slate-500 text-sm">
                          Tidak ada catatan trade yang cocok.
                        </td>
                      </tr>
                    ) : (
                      filteredTrades.map((t) => (
                        <tr key={t.id} className="hover:bg-slate-800/30 transition group">
                          <td className="py-3.5 px-4 text-xs whitespace-nowrap text-slate-400">
                            {new Date(t.date).toLocaleDateString('id-ID', { day: '2-digit', month: 'short', hour: '2-digit', minute: '2-digit' })}
                          </td>
                          <td className="py-3.5 px-4 font-bold text-slate-100">{t.pair}</td>
                          <td className="py-3.5 px-4">
                            <span className={`px-2 py-0.5 text-[10px] font-extrabold rounded ${
                              t.type === 'LONG' ? 'bg-emerald-500/20 text-emerald-400 border border-emerald-500/30' : 'bg-rose-500/20 text-rose-400 border border-rose-500/30'
                            }`}>
                              {t.type}
                            </span>
                          </td>
                          <td className="py-3.5 px-4 text-xs text-slate-300">{t.strategy}</td>
                          <td className="py-3.5 px-4 text-xs font-mono">
                            <span className="text-slate-300">{t.entryPrice}</span>
                            <span className="text-slate-500 mx-1">→</span>
                            <span className="text-slate-100 font-semibold">{t.exitPrice}</span>
                          </td>
                          <td className="py-3.5 px-4 text-xs">
                            <span className="text-slate-400 bg-slate-950 px-2 py-0.5 rounded border border-slate-800">
                              {t.source || 'Manual'}
                            </span>
                          </td>
                          <td className={`py-3.5 px-4 font-bold text-right font-mono ${t.pnl >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
                            {t.pnl >= 0 ? `+$${t.pnl}` : `-$${Math.abs(t.pnl)}`}
                          </td>
                          <td className="py-3.5 px-4 text-right font-mono text-xs font-semibold">
                            <span className={t.rMultiple >= 0 ? 'text-emerald-400' : 'text-rose-400'}>
                              {t.rMultiple >= 0 ? `+${t.rMultiple}R` : `${t.rMultiple}R`}
                            </span>
                          </td>
                          <td className="py-3.5 px-4 text-center">
                            <div className="flex items-center justify-center gap-1.5">
                              <button
                                onClick={() => handleOpenEditModal(t)}
                                className="p-1.5 text-slate-400 hover:text-emerald-400 hover:bg-slate-800 rounded-lg"
                              >
                                <Edit3 className="w-3.5 h-3.5" />
                              </button>
                              <button
                                onClick={() => handleDeleteTrade(t.id)}
                                className="p-1.5 text-slate-400 hover:text-rose-400 hover:bg-slate-800 rounded-lg"
                              >
                                <Trash2 className="w-3.5 h-3.5" />
                              </button>
                            </div>
                          </td>
                        </tr>
                      ))
                    )}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        )}

        {/* ==================== TAB 3: KALENDER PNL ==================== */}
        {activeTab === 'calendar' && (
          <div className="space-y-6">
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-6">
              <div className="flex items-center justify-between mb-6">
                <div>
                  <h3 className="text-lg font-bold text-slate-100">
                    {currentCalendarDate.toLocaleDateString('id-ID', { month: 'long', year: 'numeric' })}
                  </h3>
                  <p className="text-xs text-slate-400">Rekap PnL harian dalam tampilan kalender</p>
                </div>

                <div className="flex items-center gap-2">
                  <button
                    onClick={() => setCurrentCalendarDate(new Date(currentCalendarDate.getFullYear(), currentCalendarDate.getMonth() - 1, 1))}
                    className="p-2 bg-slate-800 text-slate-300 hover:bg-slate-700 rounded-xl transition"
                  >
                    <ChevronLeft className="w-4 h-4" />
                  </button>
                  <button
                    onClick={() => setCurrentCalendarDate(new Date())}
                    className="px-3 py-1.5 bg-slate-800 text-xs text-slate-300 hover:bg-slate-700 rounded-xl font-medium"
                  >
                    Bulan Ini
                  </button>
                  <button
                    onClick={() => setCurrentCalendarDate(new Date(currentCalendarDate.getFullYear(), currentCalendarDate.getMonth() + 1, 1))}
                    className="p-2 bg-slate-800 text-slate-300 hover:bg-slate-700 rounded-xl transition"
                  >
                    <ChevronRight className="w-4 h-4" />
                  </button>
                </div>
              </div>

              <div className="grid grid-cols-7 gap-2">
                {['Minggu', 'Senin', 'Selasa', 'Rabu', 'Kamis', 'Jumat', 'Sabtu'].map((day) => (
                  <div key={day} className="text-center text-xs font-semibold text-slate-500 py-2">
                    {day}
                  </div>
                ))}

                {(() => {
                  const year = currentCalendarDate.getFullYear();
                  const month = currentCalendarDate.getMonth();
                  const firstDayIndex = new Date(year, month, 1).getDay();
                  const daysInMonth = new Date(year, month + 1, 0).getDate();

                  const cells = [];
                  for (let i = 0; i < firstDayIndex; i++) {
                    cells.push(<div key={`empty-${i}`} className="h-24 bg-slate-950/20 rounded-xl border border-slate-900/40" />);
                  }

                  for (let d = 1; d <= daysInMonth; d++) {
                    const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}`;
                    const dayTrades = enrichedTrades.filter(t => t.date.startsWith(dateStr));
                    const dayPnL = dayTrades.reduce((sum, t) => sum + t.pnl, 0);

                    cells.push(
                      <div
                        key={d}
                        className={`h-24 p-2 rounded-xl border flex flex-col justify-between transition-all ${
                          dayTrades.length > 0
                            ? dayPnL >= 0
                              ? 'bg-emerald-950/30 border-emerald-500/30'
                              : 'bg-rose-950/30 border-rose-500/30'
                            : 'bg-slate-950/50 border-slate-800/60'
                        }`}
                      >
                        <div className="flex justify-between items-center text-xs">
                          <span className="font-semibold text-slate-400">{d}</span>
                          {dayTrades.length > 0 && (
                            <span className="text-[10px] text-slate-500 font-medium">
                              {dayTrades.length} trade
                            </span>
                          )}
                        </div>

                        {dayTrades.length > 0 ? (
                          <div>
                            <div className={`text-sm font-bold font-mono ${dayPnL >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
                              {dayPnL >= 0 ? `+$${dayPnL.toFixed(1)}` : `-$${Math.abs(dayPnL).toFixed(1)}`}
                            </div>
                          </div>
                        ) : (
                          <div className="text-[10px] text-slate-700 italic">No Trade</div>
                        )}
                      </div>
                    );
                  }

                  return cells;
                })()}
              </div>
            </div>
          </div>
        )}

        {/* ==================== TAB 4: PSIKOLOGI & ANALYTICS ==================== */}
        {activeTab === 'analytics' && (
          <div className="space-y-6">
            <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-5 flex flex-col justify-between">
                <div className="mb-4">
                  <h3 className="font-bold text-slate-200">Dampak Emosi Terhadap PnL</h3>
                  <p className="text-xs text-slate-400">Pengaruh psikologi saat eksekusi terhadap hasil</p>
                </div>

                <div className="h-64 w-full">
                  <ResponsiveContainer width="100%" height="100%">
                    <BarChart data={emotionPerformance} layout="vertical" margin={{ top: 10, right: 20, left: 20, bottom: 0 }}>
                      <CartesianGrid strokeDasharray="3 3" stroke="#1e293b" horizontal={false} />
                      <XAxis type="number" stroke="#64748b" fontSize={11} />
                      <YAxis dataKey="label" type="category" stroke="#64748b" fontSize={11} width={100} />
                      <Tooltip 
                        contentStyle={{ backgroundColor: '#0f172a', borderColor: '#334155', borderRadius: '0.75rem', color: '#f8fafc' }}
                        formatter={(val) => [`$${val}`, 'PnL Emosi']}
                      />
                      <Bar dataKey="pnl" radius={[0, 4, 4, 0]}>
                        {emotionPerformance.map((entry, index) => (
                          <Cell key={`cell-emo-${index}`} fill={entry.pnl >= 0 ? '#10b981' : '#f43f5e'} />
                        ))}
                      </Bar>
                    </BarChart>
                  </ResponsiveContainer>
                </div>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-5">
                <div className="mb-4">
                  <h3 className="font-bold text-slate-200">Performa Per Strategi</h3>
                  <p className="text-xs text-slate-400">Setup mana yang paling menguntungkan?</p>
                </div>

                <div className="space-y-3">
                  {STRATEGIES.map(strat => {
                    const stratTrades = enrichedTrades.filter(t => t.strategy === strat);
                    if (stratTrades.length === 0) return null;
                    const pnl = stratTrades.reduce((sum, t) => sum + t.pnl, 0);
                    const wins = stratTrades.filter(t => t.pnl > 0).length;
                    const winrate = ((wins / stratTrades.length) * 100).toFixed(0);

                    return (
                      <div key={strat} className="bg-slate-950/60 p-3 rounded-xl border border-slate-800 flex items-center justify-between">
                        <div>
                          <div className="text-xs font-semibold text-slate-200">{strat}</div>
                          <div className="text-[11px] text-slate-400 mt-0.5">
                            {stratTrades.length} Trade • Win Rate: <span className="text-emerald-400 font-semibold">{winrate}%</span>
                          </div>
                        </div>
                        <div className={`text-sm font-bold font-mono ${pnl >= 0 ? 'text-emerald-400' : 'text-rose-400'}`}>
                          {pnl >= 0 ? `+$${pnl.toFixed(1)}` : `-$${Math.abs(pnl).toFixed(1)}`}
                        </div>
                      </div>
                    );
                  })}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* ==================== TAB 5: KONEKSI API BROKER ==================== */}
        {activeTab === 'api' && (
          <div className="max-w-3xl mx-auto space-y-6">
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-6 space-y-6 shadow-xl">
              <div className="flex items-center justify-between border-b border-slate-800 pb-4">
                <div>
                  <h3 className="text-lg font-bold text-slate-100 flex items-center gap-2">
                    <Link2 className="w-5 h-5 text-emerald-400" />
                    Integrasi Akun Broker / Exchange
                  </h3>
                  <p className="text-xs text-slate-400 mt-0.5">
                    Hubungkan API key untuk sinkronisasi otomatis transaksi trading secara real-time
                  </p>
                </div>
                {apiConfig.isConnected && (
                  <button
                    onClick={handleDisconnectAPI}
                    className="px-3 py-1.5 text-xs bg-rose-500/20 text-rose-400 hover:bg-rose-500/30 rounded-xl border border-rose-500/30 transition font-medium"
                  >
                    Putuskan Koneksi
                  </button>
                )}
              </div>

              {/* Status Banner */}
              <div className={`p-4 rounded-xl border flex items-center justify-between ${
                apiConfig.isConnected
                  ? 'bg-emerald-950/30 border-emerald-500/30 text-emerald-300'
                  : 'bg-slate-950 border-slate-800 text-slate-400'
              }`}>
                <div className="flex items-center gap-3">
                  <div className={`p-2 rounded-lg ${apiConfig.isConnected ? 'bg-emerald-500/20' : 'bg-slate-800'}`}>
                    {apiConfig.isConnected ? <CheckCircle2 className="w-5 h-5 text-emerald-400" /> : <AlertCircle className="w-5 h-5 text-slate-400" />}
                  </div>
                  <div>
                    <div className="font-semibold text-sm text-slate-200">
                      {apiConfig.isConnected ? `Terhubung ke ${BROKERS.find(b=>b.id===apiConfig.broker)?.name}` : 'Belum Terhubung'}
                    </div>
                    <div className="text-xs text-slate-400 mt-0.5">
                      {apiConfig.isConnected
                        ? `Terakhir disinkronkan: ${apiConfig.lastSynced || 'Baru saja'}`
                        : 'Masukkan kredensial API Key di bawah untuk memulai sinkronisasi.'}
                    </div>
                  </div>
                </div>

                {apiConfig.isConnected && (
                  <button
                    onClick={handleSyncNow}
                    disabled={isSyncing}
                    className="flex items-center gap-1.5 bg-emerald-500 hover:bg-emerald-600 text-slate-950 font-bold px-3 py-1.5 rounded-xl text-xs transition"
                  >
                    <RefreshCw className={`w-3.5 h-3.5 ${isSyncing ? 'animate-spin' : ''}`} />
                    {isSyncing ? 'Syncing...' : 'Sync Live'}
                  </button>
                )}
              </div>

              {/* Form Kredensial API */}
              <div className="space-y-4">
                <div>
                  <label className="block text-xs font-semibold text-slate-300 mb-1">Pilih Broker / Platform</label>
                  <div className="grid grid-cols-2 md:grid-cols-3 gap-2.5">
                    {BROKERS.map((b) => (
                      <button
                        key={b.id}
                        type="button"
                        onClick={() => setApiConfig({ ...apiConfig, broker: b.id })}
                        className={`p-3 rounded-xl border text-left transition flex items-center gap-2.5 cursor-pointer ${
                          apiConfig.broker === b.id
                            ? 'bg-emerald-500/10 border-emerald-500 text-emerald-400'
                            : 'bg-slate-950 border-slate-800 text-slate-400 hover:border-slate-700'
                        }`}
                      >
                        <span className="text-xl">{b.icon}</span>
                        <div>
                          <div className="text-xs font-bold text-slate-200">{b.name}</div>
                          <div className="text-[10px] text-slate-500">{b.type}</div>
                        </div>
                      </button>
                    ))}
                  </div>
                </div>

                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">API Key / Account ID</label>
                  <div className="relative">
                    <Key className="w-4 h-4 text-slate-500 absolute left-3 top-1/2 -translate-y-1/2" />
                    <input
                      type="text"
                      placeholder="Masukkan API Key..."
                      value={apiConfig.apiKey}
                      onChange={(e) => setApiConfig({ ...apiConfig, apiKey: e.target.value })}
                      className="w-full bg-slate-950 border border-slate-800 rounded-xl pl-9 pr-4 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                    />
                  </div>
                </div>

                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">API Secret / Private Key</label>
                  <div className="relative">
                    <Lock className="w-4 h-4 text-slate-500 absolute left-3 top-1/2 -translate-y-1/2" />
                    <input
                      type={showSecret ? 'text' : 'password'}
                      placeholder="Masukkan API Secret..."
                      value={apiConfig.apiSecret}
                      onChange={(e) => setApiConfig({ ...apiConfig, apiSecret: e.target.value })}
                      className="w-full bg-slate-950 border border-slate-800 rounded-xl pl-9 pr-10 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                    />
                    <button
                      type="button"
                      onClick={() => setShowSecret(!showSecret)}
                      className="absolute right-3 top-1/2 -translate-y-1/2 text-slate-500 hover:text-slate-300"
                    >
                      {showSecret ? <EyeOff className="w-4 h-4" /> : <Eye className="w-4 h-4" />}
                    </button>
                  </div>
                </div>

                {apiConfig.broker.startsWith('mt') && (
                  <div>
                    <label className="block text-xs font-medium text-slate-400 mb-1">Server Broker (MetaTrader)</label>
                    <div className="relative">
                      <Server className="w-4 h-4 text-slate-500 absolute left-3 top-1/2 -translate-y-1/2" />
                      <input
                        type="text"
                        placeholder="contoh: ICMarkets-Live01"
                        value={apiConfig.server}
                        onChange={(e) => setApiConfig({ ...apiConfig, server: e.target.value })}
                        className="w-full bg-slate-950 border border-slate-800 rounded-xl pl-9 pr-4 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                      />
                    </div>
                  </div>
                )}

                <div className="pt-2 flex items-center justify-between">
                  <span className="text-xs text-slate-400">
                    * Kredensial disimpan lokal di browser & dienkripsi.
                  </span>
                  {!apiConfig.isConnected && (
                    <button
                      onClick={handleConnectAPI}
                      disabled={isSyncing}
                      className="flex items-center gap-2 bg-emerald-500 hover:bg-emerald-600 text-slate-950 font-bold px-5 py-2 rounded-xl transition text-sm cursor-pointer shadow-lg shadow-emerald-500/20"
                    >
                      <Zap className="w-4 h-4 fill-current" />
                      <span>{isSyncing ? 'Menghubungkan...' : 'Hubungkan API'}</span>
                    </button>
                  )}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* ==================== TAB 6: IMPOR CSV ==================== */}
        {activeTab === 'import' && (
          <div className="max-w-3xl mx-auto space-y-6">
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-6 space-y-5 shadow-xl">
              <div>
                <h3 className="text-lg font-bold text-slate-100 flex items-center gap-2">
                  <FileSpreadsheet className="w-5 h-5 text-emerald-400" />
                  Impor Berkas Trading Statement (CSV)
                </h3>
                <p className="text-xs text-slate-400 mt-0.5">
                  Unggah file CSV export dari MT4/MT5, Binance, atau Bybit untuk mengimpor transaksi secara massal
                </p>
              </div>

              {importNotice && (
                <div className={`p-3.5 rounded-xl border text-xs flex items-center gap-2 ${
                  importNotice.type === 'success'
                    ? 'bg-emerald-950/30 border-emerald-500/30 text-emerald-300'
                    : 'bg-rose-950/30 border-rose-500/30 text-rose-300'
                }`}>
                  {importNotice.type === 'success' ? <Check className="w-4 h-4 text-emerald-400" /> : <AlertCircle className="w-4 h-4 text-rose-400" />}
                  <span>{importNotice.text}</span>
                </div>
              )}

              {/* Drag & Drop Zone */}
              <div 
                onClick={() => fileInputRef.current?.click()}
                className="border-2 border-dashed border-slate-800 hover:border-emerald-500/50 bg-slate-950/50 hover:bg-slate-950 rounded-2xl p-8 text-center cursor-pointer transition group"
              >
                <input
                  type="file"
                  ref={fileInputRef}
                  onChange={handleFileUpload}
                  accept=".csv,.txt"
                  className="hidden"
                />
                <Upload className="w-10 h-10 text-slate-500 group-hover:text-emerald-400 transition mx-auto mb-3" />
                <div className="text-sm font-semibold text-slate-200">
                  Klik untuk memilih file CSV atau seret file ke sini
                </div>
                <div className="text-xs text-slate-500 mt-1">
                  Format yang didukung: Standard CSV (Date, Pair, Type, Entry, Exit, Lot, Fee)
                </div>
              </div>

              {/* Paste Raw CSV */}
              <div className="space-y-2">
                <label className="block text-xs font-semibold text-slate-300">Atau Tempel Teks CSV Secara Langsung</label>
                <textarea
                  rows="4"
                  placeholder="Date, Pair, Type, Entry, Exit, Lot, Fee, Notes&#10;2026-10-25 10:00, EURUSD, LONG, 1.0850, 1.0890, 0.5, 2.0, Retest SNR"
                  value={csvText}
                  onChange={(e) => setCsvText(e.target.value)}
                  className="w-full bg-slate-950 border border-slate-800 rounded-xl p-3 text-xs text-slate-200 font-mono focus:outline-none focus:border-emerald-500 resize-none"
                />
                <button
                  onClick={() => handleParseCSV(csvText)}
                  disabled={!csvText.trim()}
                  className="w-full bg-emerald-500 hover:bg-emerald-600 disabled:opacity-50 text-slate-950 font-bold py-2.5 rounded-xl text-xs transition cursor-pointer shadow-lg shadow-emerald-500/20"
                >
                  Proses & Impor Data Teks CSV
                </button>
              </div>
            </div>
          </div>
        )}

      </main>

      {/* ==================== MODAL FORM ADD / EDIT TRADE ==================== */}
      {isModalOpen && (
        <div className="fixed inset-0 z-50 bg-slate-950/80 backdrop-blur-sm flex items-center justify-center p-4 overflow-y-auto">
          <div className="bg-slate-900 border border-slate-800 w-full max-w-2xl rounded-2xl p-6 shadow-2xl space-y-5 my-8">
            <div className="flex items-center justify-between border-b border-slate-800 pb-4">
              <h3 className="text-lg font-bold text-slate-100">
                {editingTrade ? 'Edit Catatan Trade' : 'Catat Trade Baru'}
              </h3>
              <button onClick={() => setIsModalOpen(false)} className="text-slate-400 hover:text-slate-200 p-1">
                ✕
              </button>
            </div>

            <form onSubmit={handleFormSubmit} className="space-y-4">
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Tanggal & Waktu</label>
                  <input
                    type="datetime-local"
                    required
                    value={formData.date}
                    onChange={(e) => setFormData({ ...formData, date: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Pair / Aset</label>
                  <input
                    type="text"
                    required
                    placeholder="misal: XAUUSD, BTCUSDT, BBCA"
                    value={formData.pair}
                    onChange={(e) => setFormData({ ...formData, pair: e.target.value.toUpperCase() })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  />
                </div>
              </div>

              <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Tipe Posisi</label>
                  <select
                    value={formData.type}
                    onChange={(e) => setFormData({ ...formData, type: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  >
                    <option value="LONG">LONG (Buy)</option>
                    <option value="SHORT">SHORT (Sell)</option>
                  </select>
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Strategi / Setup</label>
                  <select
                    value={formData.strategy}
                    onChange={(e) => setFormData({ ...formData, strategy: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  >
                    {STRATEGIES.map(s => <option key={s} value={s}>{s}</option>)}
                  </select>
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Lot / Ukuran Posisi</label>
                  <input
                    type="number"
                    step="any"
                    required
                    value={formData.lotSize}
                    onChange={(e) => setFormData({ ...formData, lotSize: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  />
                </div>
              </div>

              <div className="grid grid-cols-2 md:grid-cols-4 gap-3">
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Entry Price</label>
                  <input
                    type="number"
                    step="any"
                    required
                    value={formData.entryPrice}
                    onChange={(e) => setFormData({ ...formData, entryPrice: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Exit Price</label>
                  <input
                    type="number"
                    step="any"
                    required
                    value={formData.exitPrice}
                    onChange={(e) => setFormData({ ...formData, exitPrice: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Stop Loss</label>
                  <input
                    type="number"
                    step="any"
                    value={formData.stopLoss}
                    onChange={(e) => setFormData({ ...formData, stopLoss: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Take Profit</label>
                  <input
                    type="number"
                    step="any"
                    value={formData.takeProfit}
                    onChange={(e) => setFormData({ ...formData, takeProfit: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 font-mono"
                  />
                </div>
              </div>

              <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Komisi / Fee ($)</label>
                  <input
                    type="number"
                    step="any"
                    value={formData.fee}
                    onChange={(e) => setFormData({ ...formData, fee: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Risiko $ (1R)</label>
                  <input
                    type="number"
                    step="any"
                    value={formData.riskAmount}
                    onChange={(e) => setFormData({ ...formData, riskAmount: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  />
                </div>
                <div>
                  <label className="block text-xs font-medium text-slate-400 mb-1">Kondisi Emosi</label>
                  <select
                    value={formData.emotion}
                    onChange={(e) => setFormData({ ...formData, emotion: e.target.value })}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-emerald-500"
                  >
                    {EMOTION_OPTIONS.map(opt => (
                      <option key={opt.value} value={opt.value}>{opt.label}</option>
                    ))}
                  </select>
                </div>
              </div>

              <div>
                <label className="block text-xs font-medium text-slate-400 mb-1">Catatan & Evaluasi Trade</label>
                <textarea
                  rows="3"
                  placeholder="Alasan entry, situasi pasar, evaluasi..."
                  value={formData.notes}
                  onChange={(e) => setFormData({ ...formData, notes: e.target.value })}
                  className="w-full bg-slate-950 border border-slate-800 rounded-xl p-3 text-sm text-slate-200 focus:outline-none focus:border-emerald-500 resize-none"
                />
              </div>

              <div className="flex items-center justify-end gap-3 pt-3 border-t border-slate-800">
                <button
                  type="button"
                  onClick={() => setIsModalOpen(false)}
                  className="px-4 py-2 text-xs font-medium text-slate-400 hover:text-slate-200 hover:bg-slate-800 rounded-xl transition"
                >
                  Batal
                </button>
                <button
                  type="submit"
                  className="px-5 py-2 text-xs font-bold bg-emerald-500 hover:bg-emerald-600 text-slate-950 rounded-xl transition shadow-lg shadow-emerald-500/20"
                >
                  Simpan Catatan Trade
                </button>
              </div>
            </form>
          </div>
        </div>
      )}
    </div>
  );
}
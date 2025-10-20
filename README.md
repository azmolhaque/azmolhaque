import React, { useState, useEffect, useCallback } from 'react';
import { Shield, BarChart, AlertTriangle, Activity, Zap, Server, Clock } from 'lucide-react';

// --- Utility Functions and Initial Data ---

// Helper to generate a random IP address for simulation
const generateRandomIP = () => {
  return Array(4).fill(0).map(() => Math.floor(Math.random() * 256)).join('.');
};

// Mock initial metrics
const initialMetrics = {
  attacksBlocked: 12450,
  criticalAlerts: 18,
  totalTraffic: 5.2, // GB
  threatLevel: 3, // 1 (Low) to 5 (Critical)
};

// Mock list of threat types and severities
const THREAT_TYPES = ['Phishing Attempt', 'DDoS Attack', 'SQL Injection', 'Malware Download', 'Port Scan'];
const SEVERITIES = ['High', 'Medium', 'Low', 'Critical'];

// Function to generate a new simulated threat
const generateNewThreat = () => {
  const severityIndex = Math.floor(Math.random() * SEVERITIES.length);
  return {
    id: Date.now() + Math.random(),
    timestamp: new Date().toLocaleTimeString(),
    sourceIP: generateRandomIP(),
    target: 'Web Server',
    type: THREAT_TYPES[Math.floor(Math.random() * THREAT_TYPES.length)],
    severity: SEVERITIES[severityIndex],
  };
};

// --- Component Definitions ---

// Card Component for consistent styling
const DashboardCard = ({ title, children, icon: Icon }) => (
  <div className="bg-gray-800 p-4 lg:p-6 rounded-xl shadow-lg border border-gray-700/50 transition duration-300 hover:border-blue-500/50 flex flex-col">
    <div className="flex items-center justify-between mb-3">
      <h2 className="text-sm font-semibold text-gray-300 uppercase tracking-wider">{title}</h2>
      {Icon && <Icon className="w-5 h-5 text-blue-400" />}
    </div>
    {children}
  </div>
);

// Metric Display Component
const MetricDisplay = ({ label, value, unit, icon: Icon, colorClass }) => (
  <div className="flex items-center p-3 bg-gray-700/50 rounded-lg">
    <div className={`p-2 rounded-full ${colorClass} bg-opacity-20`}>
      <Icon className={`w-6 h-6 ${colorClass}`} />
    </div>
    <div className="ml-4">
      <p className="text-xl font-bold text-white leading-none">{value}</p>
      <p className="text-xs text-gray-400">{label} {unit && <span className="font-medium ml-0.5">{unit}</span>}</p>
    </div>
  </div>
);

// Threat Severity Badge
const SeverityBadge = ({ severity }) => {
  let color = '';
  switch (severity) {
    case 'Critical': color = 'bg-red-600 text-white'; break;
    case 'High': color = 'bg-red-500 text-white'; break;
    case 'Medium': color = 'bg-yellow-500 text-gray-900'; break;
    case 'Low': color = 'bg-green-500 text-gray-900'; break;
    default: color = 'bg-gray-500 text-white';
  }
  return (
    <span className={`px-2 py-0.5 text-xs font-semibold rounded-full ${color}`}>
      {severity}
    </span>
  );
};

// Main Application Component
const App = () => {
  const [metrics, setMetrics] = useState(initialMetrics);
  const [threats, setThreats] = useState([]);
  const [trafficData, setTrafficData] = useState(Array(10).fill(0).map(() => Math.floor(Math.random() * 100)));

  // Simulate real-time data updates
  useEffect(() => {
    const threatInterval = setInterval(() => {
      // 1. Generate new threat (with 40% chance)
      if (Math.random() < 0.4) {
        const newThreat = generateNewThreat();
        setThreats(prev => [newThreat, ...prev].slice(0, 10)); // Keep max 10 recent threats
        if (newThreat.severity === 'Critical') {
          setMetrics(prev => ({ ...prev, criticalAlerts: prev.criticalAlerts + 1 }));
        }
        if (newThreat.severity !== 'Low') {
            setMetrics(prev => ({ ...prev, attacksBlocked: prev.attacksBlocked + 1 }));
        }
      }

      // 2. Update traffic data
      setTrafficData(prev => {
        const newData = [...prev.slice(1)];
        const lastValue = newData[newData.length - 1] || 50;
        // Simulate fluctuating traffic (min 10, max 90)
        const nextValue = Math.min(90, Math.max(10, lastValue + Math.floor(Math.random() * 21) - 10));
        newData.push(nextValue);
        return newData;
      });

      // 3. Update total traffic (GB)
      setMetrics(prev => ({
        ...prev,
        totalTraffic: parseFloat((prev.totalTraffic + 0.001 * Math.random()).toFixed(2))
      }));

    }, 1500); // Update every 1.5 seconds

    return () => clearInterval(threatInterval);
  }, []);

  // Calculate Threat Progress Bar width
  const threatWidth = `${(metrics.threatLevel / 5) * 100}%`;
  let threatColor = 'bg-green-500';
  if (metrics.threatLevel > 3) threatColor = 'bg-yellow-500';
  if (metrics.threatLevel > 4) threatColor = 'bg-red-600';


  // Traffic Chart Simulation (using only CSS/divs for single-file compliance)
  const TrafficChart = useCallback(() => (
    <div className="flex h-20 w-full items-end space-x-1">
      {trafficData.map((height, index) => (
        <div
          key={index}
          className="w-1/10 bg-blue-500 rounded-t-sm transition-all duration-1000 ease-out"
          style={{ height: `${height}%` }}
        ></div>
      ))}
    </div>
  ), [trafficData]);


  return (
    <div className="min-h-screen bg-gray-900 text-gray-100 p-4 sm:p-6 lg:p-8 font-sans">
      <header className="mb-6 lg:mb-8 flex items-center justify-between border-b border-gray-700 pb-4">
        <h1 className="text-3xl sm:text-4xl font-extrabold text-blue-400 flex items-center">
          <Shield className="w-8 h-8 mr-3 text-blue-500" />
          CyberOps Dashboard
        </h1>
        <div className="hidden sm:block text-sm text-gray-400">
          Last Updated: <span className="font-mono">{new Date().toLocaleTimeString()}</span>
        </div>
      </header>

      {/* --- Main Metrics Grid (Responsive: Stacks on mobile, 3 columns on large screens) --- */}
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 lg:gap-6 mb-8">
        <MetricDisplay
          label="Attacks Blocked"
          value={metrics.attacksBlocked.toLocaleString()}
          icon={Shield}
          colorClass="text-green-400"
        />
        <MetricDisplay
          label="Critical Alerts"
          value={metrics.criticalAlerts}
          icon={AlertTriangle}
          colorClass="text-red-500"
        />
        <MetricDisplay
          label="Total Traffic"
          value={metrics.totalTraffic}
          unit="GB"
          icon={Activity}
          colorClass="text-blue-400"
        />
        <MetricDisplay
          label="Uptime"
          value="99.99"
          unit="%"
          icon={Server}
          colorClass="text-purple-400"
        />
      </div>

      {/* --- Main Dashboard Body Grid (Responsive: 1 column on mobile, 2 columns on tablet, complex on desktop) --- */}
      <div className="grid grid-cols-1 lg:grid-cols-3 gap-4 lg:gap-6">

        {/* --- Column 1: Threat Status & Traffic (Takes 2/3 width on large screens) --- */}
        <div className="lg:col-span-2 space-y-4 lg:space-y-6">

          {/* Threat Level Indicator */}
          <DashboardCard title="Overall Threat Status" icon={Zap}>
            <p className="text-2xl font-light mb-4">
                Current State: <span className="font-bold text-red-400">ELEVATED</span>
            </p>
            <div className="w-full h-3 bg-gray-700 rounded-full overflow-hidden">
              <div
                className={`h-full ${threatColor} transition-all duration-1000 ease-out`}
                style={{ width: threatWidth }}
              ></div>
            </div>
            <div className="flex justify-between text-sm mt-1 text-gray-400">
                <span>Low</span>
                <span>Critical</span>
            </div>
          </DashboardCard>

          {/* Real-time Traffic/Anomaly Chart */}
          <DashboardCard title="Network Traffic Anomaly Monitor (MB/s)">
            <TrafficChart />
            <div className="flex justify-between text-xs text-gray-400 mt-2">
                <span>15s Ago</span>
                <span>Now</span>
            </div>
            <p className="text-sm text-gray-500 mt-3">Spikes indicate potential data exfiltration or DDoS attempts.</p>
          </DashboardCard>
        </div>


        {/* --- Column 2: Recent Threat Log (Takes 1/3 width on large screens) --- */}
        <div className="lg:col-span-1">
          <DashboardCard title="Recent Threat Log" icon={Clock}>
            <div className="h-96 overflow-y-auto pr-2">
              {threats.length === 0 ? (
                <p className="text-center text-gray-500 mt-20">No recent threats detected. Checking...</p>
              ) : (
                <ul className="space-y-3">
                  {threats.map((threat) => (
                    <li key={threat.id} className="p-3 bg-gray-700 rounded-lg hover:bg-gray-700/80 transition duration-150">
                      <div className="flex justify-between items-start">
                        <SeverityBadge severity={threat.severity} />
                        <span className="text-xs text-gray-500 font-mono">{threat.timestamp}</span>
                      </div>
                      <p className="text-sm font-medium mt-1 text-white">{threat.type}</p>
                      <p className="text-xs text-gray-400">
                        <span className="font-mono">{threat.sourceIP}</span> &rarr; {threat.target}
                      </p>
                    </li>
                  ))}
                </ul>
              )}
            </div>
          </DashboardCard>
        </div>
      </div>

      <footer className="mt-8 pt-4 border-t border-gray-700 text-center text-xs text-gray-600">
        &copy; {new Date().getFullYear()} CyberOps Simulation. Data is mocked and auto-refreshing every 1.5s.
      </footer>
    </div>
  );
};

export default App;


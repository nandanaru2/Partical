import React from 'react';
import RiskBox from './RiskBox';
import './DSADashboard.css';

const DSADashboard = () => {
  return (
    <div className="dsa-dashboard">
      <div className="dsa-header">
        <h1 className="dsa-title">DATA Risk Assessment (DSA)</h1>
      </div>
      <div className="risk-box-grid">
        {[1, 2, 3, 4, 5, 6, 7, 8, 9].map((index) => (
          <RiskBox 
            key={index}
            index={index}
            title={`Section ${index}`}
            description="Brief description of this risk assessment category."
          />
        ))}
      </div>
    </div>
  );
};

export default DSADashboard;


import React from 'react';

const RiskBox = ({ index, title, description }) => {
  return (
    <div className="risk-box">
      <div className="risk-box-content">
        <div className="risk-box-image">
          <div className="placeholder-image">Image {index}</div>
        </div>
        <div className="risk-box-text">
          <h2>{title}</h2>
          <p>{description}</p>
        </div>
      </div>
      <div className="risk-box-actions">
        <button className="btn btn-details">Details</button>
        <button className="btn btn-action">Action</button>
      </div>
    </div>
  );
};

export default RiskBox;

.dsa-dashboard {
  padding: 1.5rem;
  background-color: #f3f4f6;
  min-height: 100vh;
}

.dsa-header {
  width: 100%;
  margin-bottom: 2rem;
}

@media (min-width: 768px) {
  .dsa-header {
    width: 33.333%;
  }
}

.dsa-title {
  font-size: 2.25rem;
  font-weight: bold;
  color: #1f2937;
  border-bottom: 4px solid #3b82f6;
  padding-bottom: 0.5rem;
}

.risk-box-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.5rem;
}

@media (min-width: 768px) {
  .risk-box-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .risk-box-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.risk-box {
  background-color: white;
  border-radius: 0.5rem;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
  overflow: hidden;
  transition: all 0.3s ease;
}

.risk-box:hover {
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
  transform: scale(1.05);
}

.risk-box-content {
  padding: 1rem;
}

.risk-box-image {
  height: 8rem;
  background-color: #e5e7eb;
  border-radius: 0.375rem;
  margin-bottom: 1rem;
}

.placeholder-image {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  color: #6b7280;
}

.risk-box-text h2 {
  font-size: 1.125rem;
  font-weight: 600;
  color: #1f2937;
  margin-bottom: 0.5rem;
}

.risk-box-text p {
  font-size: 0.875rem;
  color: #4b5563;
}

.risk-box-actions {
  padding: 0.5rem 1rem;
  background-color: #f9fafb;
  display: flex;
  justify-content: space-between;
}

.btn {
  padding: 0.25rem 0.75rem;
  font-size: 0.875rem;
  border-radius: 0.25rem;
  transition: background-color 0.2s ease;
}

.btn-details {
  background-color: #3b82f6;
  color: white;
}

.btn-details:hover {
  background-color: #2563eb;
}

.btn-action {
  background-color: #10b981;
  color: white;
}

.btn-action:hover {
  background-color: #059669;
}

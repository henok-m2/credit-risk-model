# Credit Risk Probability Model

## Credit Scoring Business Understanding

### 1. Impact of Basel II Accord on Model Requirements

The Basel II Accord emphasizes **risk measurement and management** for banks. This means:

- **Interpretability is crucial**: Regulators need to understand how decisions are made
- **Documentation is required**: Models must be well-documented for audits
- **Risk-weighted assets**: Capital requirements depend on risk assessments
- **Three pillars**: Minimum capital requirements, supervisory review, market discipline

In our context, we need a model that:
- Can be explained to non-technical stakeholders
- Has clear documentation of features and logic
- Allows for stress testing and scenario analysis

### 2. Proxy Variable Necessity and Risks

**Why we need a proxy variable:**
- Our dataset has transaction data but no actual "default" labels
- We need to infer credit risk from behavior patterns
- RFM (Recency, Frequency, Monetary) analysis provides behavioral proxies

**Potential business risks:**
- **Proxy mismatch**: RFM engagement ≠ credit risk (engaged customers could still default)
- **False positives**: Good customers denied credit (lost revenue)
- **False negatives**: Risky customers approved (potential losses)
- **Regulatory issues**: Proxy-based decisions may not meet regulatory standards
- **Bias**: Behavior patterns might correlate with demographics, creating discrimination

### 3. Model Selection Trade-offs

**Simple model (Logistic Regression with WoE):**
- ✅ **Pros**: Highly interpretable, easy to explain, regulatory-friendly
- ✅ **Cons**: May underperform with complex patterns, linear assumptions

**Complex model (Gradient Boosting):**
- ✅ **Pros**: Higher predictive power, handles non-linear relationships
- ✅ **Cons**: "Black box" nature, harder to explain, regulatory challenges

**Recommended approach in regulated finance:**
1. Start with interpretable models for regulatory approval
2. Use complex models for benchmarking and insights
3. Consider hybrid approaches (explainable AI techniques)
4. Document model limitations clearly

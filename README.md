# ==========================================
# Project: PeakForge
# Description:
# A peak destination for strong architecture, disciplined coding,
# and steady growth as a developer.
# ==========================================


# ---------- main.py ----------
"""
Main entry point for PeakForge.
"""

from core.architecture import Arch
from core.discipline import DisciplineEngine
from core.growth import GrowthTracker


def run():
    print("⛰ PeakForge Initialized")
    print("🧱 Strong Architecture | 🎯 Disciplined Coding | 📈 Steady Growth\n")

    architecture = ArchitectureCore()
    discipline = DisciplineEngine()
    growth = GrowthTracker()

    data = [3, 6, 9, 12]

    # Architecture check
    print("🧱 Architecture Score:", architecture.structure_score(data))

    # Disciplined execution
    print("🎯 Controlled Execution:", discipline.execute(lambda x: x + 1, data))

    # Growth tracking
    stats = {"skill": 0.7, "consistency": 0.8}
    print("📈 Growth Projection:", growth.progress(stats))


if __name__ == "__main__":
    run()


# ---------- core/architecture.py ----------
"""
Architecture module for evaluating system structure.
"""

import statistics

class ArchitectureCore:
    """Handles structural evaluation and system design metrics."""

    def structure_score(self, values):
        """Evaluate structure using variance and balance."""
        if not values:
            return 0
        mean = statistics.mean(values)
        variance = statistics.pvariance(values)
        return round(mean / (1 + variance), 3)


# ---------- core/discipline.py ----------
"""
Discipline module enforcing controlled and consistent execution.
"""

class DisciplineEngine:
    """Ensures disciplined and predictable code execution."""

    def execute(self, func, values):
        """Execute with strict control."""
        results = []
        for v in values:
            try:
                results.append(func(v))
            except Exception:
                results.append(None)
        return results

    def validate(self, values):
        """Ensure all values meet basic discipline rules."""
        return all(isinstance(v, (int, float)) for v in values)


# ---------- core/growth.py ----------
"""
Growth module for tracking developer improvement.
"""

class GrowthTracker:
    """Tracks steady improvement over time."""

    def progress(self, metrics, rate=0.1):
        """Simulate gradual growth."""
        return {
            key: round(value * (1 + rate), 3)
            for key, value in metrics.items()
        }

    def score(self, metrics):
        """Calculate overall growth score."""
        if not metrics:
            return 0
        return round(sum(metrics.values()) / len(metrics), 3)


# ---------- tests/test_architecture.py ----------
from core.architecture import ArchitectureCore

def test_structure_score():
    core = ArchitectureCore()
    assert core.structure_score([1, 2, 3]) > 0


# ---------- tests/test_discipline.py ----------
from core.discipline import DisciplineEngine

def test_execute():
    engine = DisciplineEngine()
    assert engine.execute(lambda x: x * 2, [1, 2]) == [2, 4]


# ---------- tests/test_growth.py ----------
from core.growth import GrowthTracker

def test_progress():
    tracker = GrowthTracker()
    result = tracker.progress({"skill": 1.0})
    assert result["skill"] > 1.0

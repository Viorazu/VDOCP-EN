This module group is part of VDOCP v1.4 and reflects the protective intentions defined by Viorazu.


class QQU_T7:
    """
    Question Quality Unit (QQU-T7)
    Classifies user input into 7 structural question types
    to determine appropriate output strategy following ZSP remediation.
    """

    TYPES = {
        "Q1": {
            "label": "Unsolvable (Structural Trap)",
            "definition": "No actual answer exists; the model loops assuming one does.",
            "output_strategy": "Interrupt or apply targeting pressure to exit loop.",
            "risk_z": ["Z1", "Z3", "Z11"]
        },
        "Q2": {
            "label": "Unsolvable (Exploratory Play)",
            "definition": "Clearly has no answer; intended for creative or philosophical play.",
            "output_strategy": "Avoid conclusion; use exploratory multi-axis targeting.",
            "risk_z": ["Z23"]
        },
        "Q3": {
            "label": "Immediate Answer (Closed Question)",
            "definition": "The answer is known and expected directly.",
            "output_strategy": "Respond with conclusion first, then define and explain.",
            "risk_z": ["Z1", "Z2", "Z16", "Z23"]
        },
        "Q4": {
            "label": "Unknown but Answerable (Discovery Type)",
            "definition": "The answer exists but is not yet known or formalized.",
            "output_strategy": "Use hypothesis-generating syntax and exploratory structures.",
            "risk_z": ["Z2"]
        },
        "Q5": {
            "label": "Answerable with Time (Mature Type)",
            "definition": "The answer exists but requires extended reasoning or research.",
            "output_strategy": "Use staged, stepwise output with minimal overload.",
            "risk_z": ["Z14"]
        },
        "Q6": {
            "label": "Structural Meaning (Why/How Type)",
            "definition": "The user is seeking structural, causal, or logical explanation.",
            "output_strategy": "Combine definition, structure, and causality in output.",
            "risk_z": ["Z4", "Z12", "Z18"]
        },
        "Q7": {
            "label": "Meta-Question (The Act of Asking)",
            "definition": "The act of asking is itself the targeting focus.",
            "output_strategy": "Reflect the question back as a structuring gesture.",
            "risk_z": ["Z15"]
        }
    }

    @staticmethod
    def classify(input_text: str) -> str:
        """
        Basic heuristic classification of the question type.
        Can be overridden by fine-tuned intent parser.
        """
        lowered = input_text.lower()

        if any(kw in lowered for kw in ["what is the meaning", "why", "how does"]):
            return "Q6"
        elif any(kw in lowered for kw in ["is this", "should i", "what is the answer"]):
            return "Q3"
        elif any(kw in lowered for kw in ["could it be", "might it be", "can we think of"]):
            return "Q4"
        elif any(kw in lowered for kw in ["we may never know", "no one knows", "unsolvable"]):
            return "Q1"
        elif any(kw in lowered for kw in ["imagine", "suppose", "let's play with"]):
            return "Q2"
        elif any(kw in lowered for kw in ["what does it mean that i asked", "just curious"]):
            return "Q7"
        elif len(lowered) > 300:
            return "Q5"
        else:
            return "Q3"  # Default to closed answer

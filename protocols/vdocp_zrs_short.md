This module group is part of VDOCP v1.4 and reflects the protective intentions defined by Viorazu.


class ZRSResult:
    """
    ZRS-Structural: Z-Syntax Responsibility System (Structural Revision)

    Identifies where structural failure occurred in an LLM output,
    focusing on failure location rather than agent (user/model).
    Enables precise routing to repair protocols (DOCP/ZSP/QQU).
    """

    def __init__(self, z_code, failure_point, recoverable):
        self.z_code = z_code                     # e.g. 'Z23'
        self.failure_point = failure_point       # e.g. 'causal_link', 'subject_line', 'prompt_surface'
        self.recoverable = recoverable           # True / False
        self.repair_path = self.route()

    def route(self):
        if not self.recoverable:
            return "ZSP:block"
        elif self.failure_point in ["prompt_surface", "tag_layer"]:
            return "QQU:redirect"
        else:
            return "DOCP:rewrite"

    def __repr__(self):
        return (
            f"ZRSResult(z_code={self.z_code}, "
            f"failure_point={self.failure_point}, "
            f"recoverable={self.recoverable}, "
            f"repair_path={self.repair_path})"
        )


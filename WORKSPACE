workspace(name = "toktok")

# Haskell
# =========================================================

RULES_HASKELL_VERSION = "17509e5051d9e8ccbff092c3a94594bb91141e4d"

http_archive(
    name = "io_tweag_rules_haskell",
    sha256 = "3ad4365968cbf9108e14b347f77c7d7bf4046d178d3e52a8d285feb9cdb8725c",
    strip_prefix = "rules_haskell-%s" % RULES_HASKELL_VERSION,
    urls = ["https://github.com/tweag/rules_haskell/archive/%s.tar.gz" % RULES_HASKELL_VERSION],
)

load("@io_tweag_rules_haskell//haskell:repositories.bzl", "haskell_repositories")

haskell_repositories()

load("@io_tweag_rules_haskell//haskell:ghc_bindist.bzl", "ghc_bindist")
load("//third_party/haskell:haskell.bzl", "new_cabal_package")

# This repository rule creates @ghc repository.
ghc_bindist(
  name    = "ghc",
)

register_toolchains("//:ghc")

new_cabal_package(
    package = "clock-0.7.2",
    sha256 = "886601978898d3a91412fef895e864576a7125d661e1f8abc49a2a08840e691f",
)

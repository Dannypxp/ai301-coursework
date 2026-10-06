## Plan
diagnosis - Certain combinations/patterns of words with the same meaning produce different results, Adding verbs and nouns from the failed tests in test_bias_detector.py to bias_detector.py patterns will help identify more common phrasings

scope - Scope for the project are the Bias detector functions and tests for bias_detector.py

files touched - bias_detector.py, test_bias_detector.py, I won't touch ingestion pipeline

approach - Check the words and groupings mentioned in bias_detector.py and then from the failed tests, add words missed or not included into bias_detector.py patterns for dismissive and demographic. The issue states "The regex patterns in bias_detector.py require near-exact phrase sequences (e.g. “bootcamp graduates lack rigor”) and miss natural phrasings of the same bias" so updating patterns should fix the remaining issues. Furthermore, removing the xfail markers from the 9 tests will allow the tests to correctly output (True,'') after the fixes.
test plan - 

    Environment - Docker 28.0.1, Macos 27.0, Python 3.11.15
    Reproduction Steps -
    cp .env.example .env
    docker compose up -d
    make setup
    python3 -c "
    from safety.bias_detector import BiasDetector
    print(BiasDetector.detect_bias('The candidate only attended a bootcamp, so this project lacks the rigor of a formal CS education'))"
    (False, '')

    Expected - (True, "Dismissive language about educational background")

    Actual - (False, '')

    After Fix - (True, 'Dismissive language about educational background')



risks and unknowns - how the bias_detector works like breaking down a sentence

## deviations

At first I didn't think I had to touch test_bias_detector.py but after finding the root cause, I also realized I had to remove the xfail markers to properly get the right output.
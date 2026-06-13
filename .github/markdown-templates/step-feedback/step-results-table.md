### 결과

| 점검 항목 | 상태 |
|---------|------|
{% for item in results_table %}
| {{ item.description }} | {% if item.passed %}✅ 완료{% else %}❌ 미완료{% endif %} |
{% endfor %}

{% if results_table | map(attribute="passed") | list | select("equalto", false) | list %}
위의 모든 항목을 완료한 후 다시 시도해주세요.
{% else %}
축하합니다! 모든 항목을 완료했습니다. 다음 단계로 진행합니다.
{% endif %}

---
title: プロジェクトのコントリビューターを表示する
intro: 'リポジトリへのコミットにコントリビュートした人{% ifversion fpt or ghec %}とその依存関係{% endif %}を表示できます。'
redirect_from:
  - /articles/i-don-t-see-myself-in-the-contributions-graph
  - /articles/viewing-contribution-activity-in-a-repository
  - /articles/viewing-a-projects-contributors
  - /github/visualizing-repository-data-with-graphs/viewing-a-projects-contributors
  - /github/visualizing-repository-data-with-graphs/accessing-basic-repository-data/viewing-a-projects-contributors
product: '{% data reusables.gated-features.repository-insights %}'
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Repositories
shortTitle: View project contributors
---

## コントリビューターについて

コントリビューターグラフで{% ifversion ghes or ghae %}、コミットの共作者を含めて{% endif %}、リポジトリに貢献した上位 100 人のコントリビューターを表示できます。 マージコミットと空のコミットは、このグラフでコントリビューションとして数えられません。

{% ifversion fpt or ghec %}
プロジェクトの Python 依存関係に貢献した人のリストも表示されます。 この、コミュニティコントリビューターのリストを表示するには、`https://github.com/REPO-OWNER/REPO-NAME/community_contributors` にアクセスしてください。
{% endif %}

## コントリビューターグラフにアクセスする

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.accessing-repository-graphs %}
3. 左サイドバーで [**Contributors**] をクリックします。 ![コントリビュータータブ](/assets/images/help/graphs/contributors_tab.png)
4. オプションで、特定の期間におけるコントリビューターを表示するには、クリックしてから、その期間が選択されるまでドラッグしてください。 The contributors graph sums weekly commit numbers onto each Sunday, so your time period must include a Sunday. ![コントリビュータグラフで選択した時間範囲](/assets/images/help/graphs/repo_contributors_click_drag_graph.png)

## コントリビューターのトラブルシューティング

リポジトリのコントリビュータグラフにあなたが表示されない場合、以下の理由が考えられます:
- 上位 100 人に入っていない。
- コミットがデフォルトブランチにマージされていない。
- コミットの作成に使用したメールアドレスが、{% data variables.product.product_name %} のアカウントに接続されていない。

{% tip %}

**Tip:** To list all commit contributors in a repository, see "[List repository contributors](/rest/repos/repos#list-repository-contributors)."

{% endtip %}

リポジトリ内のあなたのコミットがすべてデフォルト以外のブランチにある場合、コントリビュータグラフには表示されません。 たとえば、`gh-pages`ブランチに対して行われたコミットは、`gh-pages`がリポジトリのデフォルトのブランチでない限り、グラフに含まれません。 コミットをデフォルトブランチにマージするため、プルリクエストを作成できます。 詳しい情報については[プルリクエストについて](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)を参照してください。

コミットの作成に使用したメールアドレスが {% data variables.product.product_name %} のアカウントに接続されていない場合、コミットはアカウントにリンクされず、コントリビュータグラフに表示されません。 詳しい情報については、「[コミットメールアドレスを設定する](/articles/setting-your-commit-email-address){% ifversion not ghae %}」および「[{% data variables.product.prodname_dotcom %} アカウントにメールアドレスを追加する](/articles/adding-an-email-address-to-your-github-account){% endif %}」を参照してください。

---
title: Customer Journey Analytics で使用するスキーマの設計
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 91%

---

# Customer Journey Analytics で使用するスキーマの設計 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="スキーマを設計"
>abstract="組織内でデータ収集の要件について話し合い、Adobe Experience Platform で使用するスキーマの作成方法を決定します。この手順は、組織に合わせて調整されたスキーマを使用する推奨プロセスを使用するために表示されます。組織内のすべてのチームが調整するスキーマにより、データの取り込みが大幅に簡単になるので、この手順を正しく実行することが極めて重要です。<br><br>組織内のすべての関係者を集めて統合スキーマを調整するのにかかる推定時間は 1～2 か月です。この時間枠は、調整が必要なチームの数と、調整するディメンションと指標の数に大きく依存します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

アドビでは、Adobe Analytics から Customer Journey Analytics にアップグレードする際に、Web SDK で使用するカスタムエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。または、Adobe Analytics ExperienceEvent フィールドグループを使用するデフォルトの Adobe Analytics スキーマを使用することもできます。

カスタム XDM スキーマを使用すると、組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマが可能になります。Adobe Analytics ExperienceEvent フィールドグループを使用するデフォルトの Adobe Analytics スキーマとは異なり、カスタム XDM スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。

これらのスキーマオプションについて詳しくは、[Customer Journey Analytics のスキーマの選択](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)を参照してください。

XDM スキーマの設計を開始する際は、次の節を確認してください。

## XDM スキーマでの Adobe Analytics の制限の回避

Customer Journey Analytics の基盤となるアーキテクチャには、Adobe Analytics よりもはるかに高い柔軟性が用意されています。新しい XDM スキーマの作成は、その柔軟性を解き放つ重要な方法です。Customer Journey Analytics にアップグレードする際は、スキーマへの不要な Adobe Analytics の制限が引き継がれるのを回避します。

>[!NOTE]
>
>次の情報はまだ完成していません。 近い将来完成するでしょう。

| Adobe Analytics データアーキテクチャ | XDM スキーマアーキテクチャ |
|---------|----------|
| 個々の指標が Analytics データアーキテクチャに追加されます。<br/>例えば、Adobe Analytics では、各イベントに異なる eVar があります。 | XDM スキーマではなくデータビューで個々の指標を作成します。これにより、後で変更を行う必要がある場合に、柔軟性が高まります。<br/>例えば、Customer Journey Analytics では、スキーマに単一のイベントがあり、データビューでイベントの作成を使用します。 |
| カスタム変数を作成するには、Props と eVars が必要です。 |  |

## 組織全体のデータチームとその他の関係者の特定

>[!NOTE]
>
>この情報はまだ利用できません。 近い将来に利用可能になる予定です。

## 組織で使用されている他の Adobe Experience Platform アプリケーションを考慮します

>[!NOTE]
>
>この情報はまだ利用できません。 近い将来に利用可能になる予定です。

---
title: 変更 SQL 生成
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: b6c1b71effba17d33c035d0f1df386bf56d405b5
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039895"
---
# <a name="modification-sql-generation"></a><span data-ttu-id="91cc7-102">変更 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="91cc7-102">Modification SQL Generation</span></span>

<span data-ttu-id="91cc7-103">ここでは、SQL:1999 準拠のデータベース プロバイダーのための変更 SQL 生成モジュールを開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="91cc7-104">このモジュールは、変更コマンド ツリーを適切な SQL INSERT ステートメント、UPDATE ステートメント、または DELETE ステートメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>

<span data-ttu-id="91cc7-105">SELECT ステートメントでの SQL 生成については、「[SQL 生成](sql-generation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91cc7-105">For information about SQL generation for select statements, see [SQL Generation](sql-generation.md).</span></span>

## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="91cc7-106">変更コマンド ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="91cc7-106">Overview of Modification Command Trees</span></span>

<span data-ttu-id="91cc7-107">変更 SQL 生成モジュールは、指定された入力 DbModificationCommandTree に基づいて、データベースに固有の変更 SQL ステートメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>

<span data-ttu-id="91cc7-108">DbModificationCommandTree は、DbCommandTree から継承される変更 DML 操作 (挿入、更新、または削除操作) のオブジェクト モデル表現です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="91cc7-109">DbModificationCommandTree には、次の 3 つの実装があります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-109">There are three implementations of DbModificationCommandTree:</span></span>

- <span data-ttu-id="91cc7-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="91cc7-110">DbInsertCommandTree</span></span>

- <span data-ttu-id="91cc7-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="91cc7-111">DbUpdateCommandTree</span></span>

- <span data-ttu-id="91cc7-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="91cc7-112">DbDeleteCommandTree</span></span>

<span data-ttu-id="91cc7-113">DbModificationCommandTree と、Entity Framework によって生成されるその実装は、常に単一行の操作を表します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-113">DbModificationCommandTree and its implementations that are produced by the Entity Framework always represent a single row operation.</span></span> <span data-ttu-id="91cc7-114">ここでは、これら 3 つの種類の実装と、.NET Framework Version 3.5 における制約について説明します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>

<span data-ttu-id="91cc7-115">![図](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="91cc7-115">![Diagram](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>

<span data-ttu-id="91cc7-116">DbModificationCommandTree には、変更操作のターゲット セットを表す Target プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="91cc7-117">入力セットを定義する Target の Expression プロパティは、常に DbScanExpression です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="91cc7-118">DbScanExpression では、テーブルまたはビューを表すことができます。また、Target の "Defining Query" メタデータ プロパティが null 以外の場合は、クエリによって定義されたデータのセットを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>

<span data-ttu-id="91cc7-119">モデル内で定義クエリを使用してセットが定義されているが、対応する変更操作のための関数が指定されていない場合、クエリを表す DbScanExpression は、変更のターゲットとしてプロバイダーにのみ影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="91cc7-120">プロバイダーによっては、このようなシナリオはサポートされません (たとえば、SqlClient ではサポートされません)。</span><span class="sxs-lookup"><span data-stu-id="91cc7-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>

<span data-ttu-id="91cc7-121">DbInsertCommandTree は、コマンド ツリーとして表現される、単一行の挿入操作を表します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

<span data-ttu-id="91cc7-122">DbUpdateCommandTree は、コマンド ツリーとして表現される、単一行の更新操作を表します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>

<span data-ttu-id="91cc7-123">DbDeleteCommandTree は、コマンド ツリーとして表現される、単一行の削除操作を表します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>

### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="91cc7-124">変更コマンド ツリーのプロパティの制限</span><span class="sxs-lookup"><span data-stu-id="91cc7-124">Restrictions on Modification Command Tree Properties</span></span>

<span data-ttu-id="91cc7-125">変更コマンド ツリーのプロパティに対して、次の情報および制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-125">The following information and restrictions apply to the modification command tree properties.</span></span>

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="91cc7-126">DbInsertCommandTree および DbUpdateCommandTree の Returning</span><span class="sxs-lookup"><span data-stu-id="91cc7-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="91cc7-127">null 以外の場合、Returning は、コマンドがリーダーを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="91cc7-128">null の場合、コマンドは、影響を受けた (挿入または更新された) 行の数を示すスカラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>

<span data-ttu-id="91cc7-129">Returning 値は、挿入または更新された行に基づいて返される結果の射影を指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="91cc7-130">この値は、行を表す DbNewInstanceExpression 型である必要があります。その各引数は、対応する DbModificationCommandTree の Target への参照を表す DbVariableReferenceExpression に対する DbPropertyExpression になります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="91cc7-131">Returning プロパティで使用されている DbPropertyExpressions で表されるプロパティは、常にストア生成値または計算値となります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="91cc7-132">DbInsertCommandTree では、行が挿入されるテーブルの 1 つ以上のプロパティがストア生成値または計算値として指定されている (ssdl で StoreGeneratedPattern.Identity または StoreGeneratedPattern.Computed とマークされている) 場合、Returning は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="91cc7-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="91cc7-133">DbUpdateCommandTrees では、行が更新されるテーブルの 1 つ以上のプロパティがストア計算値として指定されている (ssdl で StoreGeneratedPattern.Computed とマークされている) 場合、Returning は null ではありません。</span><span class="sxs-lookup"><span data-stu-id="91cc7-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="91cc7-134">DbInsertCommandTree および DbUpdateCommandTree の SetClauses</span><span class="sxs-lookup"><span data-stu-id="91cc7-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="91cc7-135">SetClauses は、挿入または更新操作を定義する insert set 句または update set 句のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>

<span data-ttu-id="91cc7-136">リストの要素は DbModificationClause 型として指定され、挿入または更新の変更操作において 1 つの句を指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-136">The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation.</span></span> <span data-ttu-id="91cc7-137">DbSetClause は DbModificationClause を継承し、変更操作においてプロパティの値を設定する句を指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-137">DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property.</span></span> <span data-ttu-id="91cc7-138">.NET Framework のバージョン 3.5 以降では、SetClauses のすべての要素が SetClause 型です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-138">Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.</span></span>

<span data-ttu-id="91cc7-139">Property は、更新する必要があるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-139">Property specifies the property that should be updated.</span></span> <span data-ttu-id="91cc7-140">これは常に、対応する DbModificationCommandTree の Target への参照を表す、DbVariableReferenceExpression に対する DbPropertyExpression です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-140">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

<span data-ttu-id="91cc7-141">Value は、プロパティを更新するための新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-141">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="91cc7-142">DbConstantExpression 型または DbNullExpression 型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-142">It is either of type DbConstantExpression or DbNullExpression.</span></span>

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="91cc7-143">DbUpdateCommandTree および DbDeleteCommandTree の Predicate</span><span class="sxs-lookup"><span data-stu-id="91cc7-143">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>

<span data-ttu-id="91cc7-144">Predicate は、ターゲット コレクションのどのメンバーを更新または削除する必要があるかを判定するために使用される述語を指定します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-144">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="91cc7-145">これは、DbExpressions の次のサブセットから構成される式ツリーです。</span><span class="sxs-lookup"><span data-stu-id="91cc7-145">It is an expression tree built of the following subset of DbExpressions:</span></span>

- <span data-ttu-id="91cc7-146">Equals 型の DbComparisonExpression。右辺の子は以下のように制限される DbPropertyExpression、左辺の子は DbConstantExpression です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-146">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExpression as restricted below and the left child a DbConstantExpression.</span></span>

- <span data-ttu-id="91cc7-147">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="91cc7-147">DbConstantExpression</span></span>

- <span data-ttu-id="91cc7-148">以下のように制限される、DbPropertyExpression に対する DbIsNullExpression。</span><span class="sxs-lookup"><span data-stu-id="91cc7-148">DbIsNullExpression over a DbPropertyExpression as restricted below</span></span>

- <span data-ttu-id="91cc7-149">対応する DbModificationCommandTree の Target への参照を表す、DbVariableReferenceExpression に対する DbPropertyExpression。</span><span class="sxs-lookup"><span data-stu-id="91cc7-149">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

- <span data-ttu-id="91cc7-150">DbAndExpression。</span><span class="sxs-lookup"><span data-stu-id="91cc7-150">DbAndExpression</span></span>

- <span data-ttu-id="91cc7-151">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="91cc7-151">DbNotExpression</span></span>

- <span data-ttu-id="91cc7-152">DbOrExpression。</span><span class="sxs-lookup"><span data-stu-id="91cc7-152">DbOrExpression</span></span>

## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="91cc7-153">サンプル プロバイダーでの変更 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="91cc7-153">Modification SQL Generation in the Sample Provider</span></span>

<span data-ttu-id="91cc7-154">[Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) では、Entity Framework をサポートする ADO.NET データ プロバイダーのコンポーネントが示されています。</span><span class="sxs-lookup"><span data-stu-id="91cc7-154">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the components of ADO.NET Data Providers that support the Entity Framework.</span></span> <span data-ttu-id="91cc7-155">このサンプルは、SQL Server 2005 データベースを対象としており、System.Data.SqlClient ADO.NET 2.0 データ プロバイダーの最上位にラッパーとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-155">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>

<span data-ttu-id="91cc7-156">SQL Generation\DmlSqlGenerator.cs ファイル内にあるサンプル プロバイダーの変更 SQL 生成モジュールは、DbModificationCommandTree を入力として受け取り、単一の変更 SQL ステートメントを生成します。この後に、DbModificationCommandTree によって指定された場合にリーダーを返す SELECT ステートメントが続く場合もあります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-156">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="91cc7-157">生成されたコマンドの構造は、対象の SQL Server データベースの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-157">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>

### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="91cc7-158">ヘルパー クラス: ExpressionTranslator</span><span class="sxs-lookup"><span data-stu-id="91cc7-158">Helper Classes: ExpressionTranslator</span></span>

<span data-ttu-id="91cc7-159">ExpressionTranslator は、DbExpression 型のすべての変更コマンド ツリー プロパティのための一般的な軽量のトランスレーターです。</span><span class="sxs-lookup"><span data-stu-id="91cc7-159">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="91cc7-160">このトランスレーターは、変更コマンド ツリーのプロパティを制限する式の型の変換のみをサポートし、特定の制約を考慮して構築されています。</span><span class="sxs-lookup"><span data-stu-id="91cc7-160">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>

<span data-ttu-id="91cc7-161">以降では、特定の式の型へのアクセスについて説明します (重要度の低い変換を含むノードは省略しています)。</span><span class="sxs-lookup"><span data-stu-id="91cc7-161">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>

### <a name="dbcomparisonexpression"></a><span data-ttu-id="91cc7-162">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="91cc7-162">DbComparisonExpression</span></span>

<span data-ttu-id="91cc7-163">preserveMemberValues を true に設定して ExpressionTranslator を構築したときに、右辺の定数が (DbNullExpression ではなく) DbConstantExpression である場合、左辺のオペランド (DbPropertyExpressions) が DbConstantExpression に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-163">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="91cc7-164">これは、返される Select ステートメントを、影響を受けた行を識別するために生成する必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-164">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>

### <a name="dbconstantexpression"></a><span data-ttu-id="91cc7-165">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="91cc7-165">DbConstantExpression</span></span>

<span data-ttu-id="91cc7-166">アクセスされる定数のそれぞれに対して、パラメーターが作成されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-166">For each visited constant a parameter is created.</span></span>

### <a name="dbpropertyexpression"></a><span data-ttu-id="91cc7-167">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="91cc7-167">DbPropertyExpression</span></span>

<span data-ttu-id="91cc7-168">DbPropertyExpression のインスタンスが常に入力テーブルを表す場合、生成によって別名が作成される状況を除き (テーブル変数が使用されたときの更新シナリオでのみこの状況が発生します)、入力に別名を指定する必要はありません。変換には既定でプロパティ名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-168">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>

## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="91cc7-169">挿入 SQL コマンドの生成</span><span class="sxs-lookup"><span data-stu-id="91cc7-169">Generating an Insert SQL Command</span></span>

<span data-ttu-id="91cc7-170">サンプル プロバイダーで指定されている DbInsertCommandTree に対して生成される挿入コマンドは、以下に示す 2 つの挿入テンプレートのどちらかに基づいています。</span><span class="sxs-lookup"><span data-stu-id="91cc7-170">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>

<span data-ttu-id="91cc7-171">1 つ目のテンプレートには、SetClauses のリストの値を受け取って挿入を実行するコマンドと、挿入された行の Returning プロパティが null 以外の場合にその Returning プロパティで指定されたプロパティを返す SELECT ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91cc7-171">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="91cc7-172">行が挿入された場合、述語要素 "\@@ROWCOUNT > 0" は true になります。</span><span class="sxs-lookup"><span data-stu-id="91cc7-172">The predicate element "\@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="91cc7-173">述語要素 "keyMemberI =  keyValueI &#124; scope_identity()" は、keyMemberI がストア生成キーの場合にのみ "keyMemberI =  scope_identity()" という構造をとります。これは、ID (ストア生成の ID) 列に挿入された最後の ID 値が scope_identity() によって返されるためです。</span><span class="sxs-lookup"><span data-stu-id="91cc7-173">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="91cc7-174">2 番目のテンプレートが必要となるのは、挿入操作で行の挿入を指定するとき、主キーがストア生成値であるが整数型ではないために、scope_identity() でそのキーを使用できない場合です。</span><span class="sxs-lookup"><span data-stu-id="91cc7-174">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="91cc7-175">このテンプレートは、複合ストア生成キーがある場合にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-175">It is also used if there is a compound store-generated key.</span></span>

```sql
-- second insert template
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)

INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning_over_t>
 FROM @generated_keys  AS g
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN
 WHERE @@ROWCOUNT > 0
```

<span data-ttu-id="91cc7-176">サンプル プロバイダーに含まれるモデルの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-176">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="91cc7-177">この例では、DbInsertCommandTree から挿入コマンドを生成しています。</span><span class="sxs-lookup"><span data-stu-id="91cc7-177">It generates an insert command from a DbInsertCommandTree.</span></span>

<span data-ttu-id="91cc7-178">次のコードは、Category を挿入します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-178">The following code inserts a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="91cc7-179">このコードでは、プロバイダーに渡される次のコマンド ツリーを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-179">This code produces the following command tree, which is passed to the provider:</span></span>

```output
DbInsertCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
| | |_Property
| | | |_Var(target).CategoryName
| | |_Value
| |   |_'Test Category'
| |_DbSetClause
| | |_Property
| | | |_Var(target).Description
| | |_Value
| |   |_'A new category for testing'
| |_DbSetClause
|   |_Property
|   | |_Var(target).Picture
|   |_Value
|     |_null
|_Returning
  |_NewInstance : Record['CategoryID'=Edm.Int32]
    |_Column : 'CategoryID'
      |_Var(target).CategoryID
```

<span data-ttu-id="91cc7-180">サンプル プロバイダーによって生成されるストア コマンドは、次の SQL ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="91cc7-180">The store command that the sample provider produces is the following SQL statement:</span></span>

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a><span data-ttu-id="91cc7-181">更新 SQL コマンドの生成</span><span class="sxs-lookup"><span data-stu-id="91cc7-181">Generating an Update SQL Command</span></span>

<span data-ttu-id="91cc7-182">指定された DbUpdateCommandTree に対して、以下に示すテンプレートに基づいて、更新コマンドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-182">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="91cc7-183">set 句が指定されない場合にのみ、仮の set 句 ("@i = 0") が設定されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-183">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="91cc7-184">これは、ストア計算列が再計算されるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="91cc7-184">This is to ensure that any store-computed columns are recomputed.</span></span>

<span data-ttu-id="91cc7-185">Returning プロパティが null でない場合にのみ、SELECT ステートメントが生成され、Returning プロパティに指定されたプロパティが返されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-185">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>

<span data-ttu-id="91cc7-186">次の例では、サンプル プロバイダーに含まれるモデルを使用して、更新コマンドを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-186">The following example uses the model that is included with the sample provider to generate an update command.</span></span>

<span data-ttu-id="91cc7-187">次のユーザー コードは、Category を更新します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-187">The following user code updates a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="91cc7-188">このユーザー コードは、プロバイダーに渡される次のコマンド ツリーを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-188">This user code produces the following command tree, which is passed to the provider:</span></span>

```output
DbUpdateCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
|   |_Property
|   | |_Var(target).CategoryName
|   |_Value
|     |_'New test name'
|_Predicate
| |_
|   |_Var(target).CategoryID
|   |_=
|   |_10
|_Returning
```

<span data-ttu-id="91cc7-189">サンプル プロバイダーによって、次のストア コマンドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-189">The sample provider produces the following store command:</span></span>

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="91cc7-190">削除 SQL コマンドの生成</span><span class="sxs-lookup"><span data-stu-id="91cc7-190">Generating a Delete SQL Command</span></span>

<span data-ttu-id="91cc7-191">指定された DbDeleteCommandTree に対して、以下に示すテンプレートに基づいて、削除コマンドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-191">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

<span data-ttu-id="91cc7-192">次の例では、サンプル プロバイダーに含まれるモデルを使用して、削除コマンドを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-192">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>

<span data-ttu-id="91cc7-193">次のユーザー コードは、Category を削除します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-193">The following user code deletes a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="91cc7-194">このユーザー コードは、プロバイダーに渡される次のコマンド ツリーを生成します。</span><span class="sxs-lookup"><span data-stu-id="91cc7-194">This user code produces the following command tree, which is passed to the provider.</span></span>

```output
DbDeleteCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_Predicate
  |_
    |_Var(target).CategoryID
    |_=
    |_10
```

<span data-ttu-id="91cc7-195">サンプル プロバイダーによって、次のストア コマンドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="91cc7-195">The following store command is produced by the sample provider:</span></span>

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a><span data-ttu-id="91cc7-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="91cc7-196">See also</span></span>

- [<span data-ttu-id="91cc7-197">Entity Framework データ プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="91cc7-197">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)

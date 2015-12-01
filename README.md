# angular
/*   ng-repeat + animate               */
<body ng-app="ngAnimate">
  <div ng-init="friends = [
  {name:'John', age:25, gender:'boy'},
  {name:'Jessie', age:30, gender:'girl'},
  {name:'Johanna', age:28, gender:'girl'},
  {name:'Joy', age:15, gender:'girl'},
  {name:'Mary', age:28, gender:'girl'},
  {name:'Peter', age:95, gender:'boy'},
  {name:'Sebastian', age:50, gender:'boy'},
  {name:'Erika', age:27, gender:'girl'},
  {name:'Patrick', age:40, gender:'boy'},
  {name:'Samantha', age:60, gender:'girl'}
]">
  I have {{friends.length}} friends. They are:
  <input type="search" ng-model="q" placeholder="filter friends..." aria-label="filter friends" />
  <ul class="example-animate-container">
    <li class="animate-repeat" ng-repeat="friend in friends | filter:q as results">
      [{{$index + 1}}] {{friend.name}} who is {{friend.age}} years old.
    </li>
    <li class="animate-repeat" ng-if="results.length == 0">
      <strong>No results found...</strong>
    </li>
  </ul>
</div>
</body>
.animate-repeat.ng-move,
.animate-repeat.ng-enter,
.animate-repeat.ng-leave {
  transition:all ease 0.7s;
}

.animate-repeat.ng-leave.ng-leave-active,
.animate-repeat.ng-move,
.animate-repeat.ng-enter {
  opacity:0;
  max-height:0;
}

.animate-repeat.ng-leave,
.animate-repeat.ng-move.ng-move-active,
.animate-repeat.ng-enter.ng-enter-active {
  opacity:1;
  max-height:60px;
}

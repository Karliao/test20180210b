
rails API

https://apidock.com/rails

--------------------------------------------
echo "# test20180210b" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:Karliao/test20180210b.git
git push -u origin master

git push -u remote_repo local_brach

--------------------------------------------

<a href="about.html">About</a>
about.html must be put in public directory
link_to can only use controller path


--------------------------------------------

  def index
    # @topics = Topic.all
    # @topics = Topic.all.order(votes: :desc)
    @topics = Topic.joins("LEFT JOIN (SELECT topic_id, count(*) c from votes group by topic_id) v  on topics.id=v.topic_id").order("v.c DESC")
  end

